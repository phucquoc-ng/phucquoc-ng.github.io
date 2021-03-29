---
layout: post
title: Flutter Isolate giải quyết được gì?
date: 2021-03-29 11:58:08
tags: ['flutter','dart']
---
Một ngày đẹpt trời bạn gặp 1 tasks bên dưới bạn sẽ giải quyết thế nào?

- Bạn đang có ý định call api và xử lí response khi server trả về kết quả, và response đó chứa hàng triệu bản ghi/giá trị, mà nếu làm theo cách thông thường sẽ làm cho UI của bạn bị treo
- Bạn cần edit một ảnh trên app mà ảnh đó cực kì lớn, có thể gây treo hoặc lag app

Đến đây bạn chắc đã biết có rất nhiều cách có thể giải quyết vấn đề trên đúng không?

Nhưng hum nay mình chỉ đề cập đến **Flutter Isolate** 

Vậy **Flutter Isolate** là gì?

Để dễ hiểu hơn ta có thể thấy trong một số game FPS như Counter Strike, COD,... bạn có thể thấy cứ mỗi khi bạn bắn súng, sẽ có nhiều task cần được thực thi, ví dụ như phát tiếng súng nổ, thay đổi số lượng đạn còn lại, giảm máu của đối tượng bị trúng đạn,... Tất cả những task này được phân chia thành nhiều thread khác nhau, xử lí song song ở trong các **isolate** riêng biệt (isolate và thread có thể gọi thay cho nhau vì thực chất isolate là thứ mà Dart gọi để ám chỉ việc multi threading)

Những ngôn ngữ như JAVA hay C++ chia sẻ bộ nhớ [heap](https://docs.oracle.com/cd/E13150_01/jrockit_jvm/jrockit/geninfo/diagnos/garbage_collect.html) của chúng với thread, nhưng với Flutter, tất cả các isolate đều có một bộ nhớ riêng biệt và hoạt động độc lập. Chính vì nó có bộ nhớ riêng nên chúng không cần phải *locking* giống như bên thread, vì vậy khi nó đã hoàn thành xong task, thì bộ nhớ đó sẽ tự động được giải phóng bằng *garbage collection*.

![dart isolate](/Users/mbp0031/QuocNg/phucquoc-ng.github.io/source/_images/dart_isolate.jpeg)

Bất kể một chương trình Dart nào đều run trên một hoặc nhiều Isolate (chúng ta hay thường gọi là Dart Isolate). 

Các thành phần cơ bản của **Dart Isolate**:

- **Heap:** Nơi lưu trữ các object được cấp phát trong chương trình
- **Mutator Thread:** Thread này sẽ thực thi Dart code (viết trên C)
- **Helper Thread:** Một Isolate có thể có nhiều helper thread, công việc chính là xử lý những tác vụ bên trong Dart VM ví dụ như GC, JIT ...

💥 Vùng **Heap** của các **Isolate** không thể liên hệ với nhau

💥Giữa các **Isolate** không có sự chia sẻ về **memory** và để giao tiếp giữa chúng chúng ta phải sử dụng các **message** gửi vào các **Ports** sau đó lắng nghe tại các **Ports** đó để lấy data về.

> Để sử dụng những lợi ích nêu trên, Flutter đã để dành riêng cho mỗi isolate một bộ nhớ riêng, chính vì thế nên họ mới đặt tên nó là isolate (mang ý nghĩa *cô lập*, *độc lập* trong tiếng Việt)

Vậy để tống kết lại, bạn sẽ cần đến isolate khi bạn nghĩ rằng task đó sẽ rất "nặng", cần rất nhiều sự tính toán và tài nguyên cho nó, và bạn không muốn thực hiện nó trên UI thread vì nó sẽ ảnh hưởng đến UI của bạn.