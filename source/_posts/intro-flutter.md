---
layout: post
title: Giới thiệu về Flutter
date: 2020-10-12 14:46:13
tags:['flutter', 'dart']
---

**Flutter** được phát triển nhằm giải quyết bài toán thường gặp trong mobile là **Fast Development** và **Native Performance**. Nếu như React Native chỉ đảm bảo **FD** và code native thuần chỉ đảm bảo **NP** thì **Flutter** làm được cả 2 điều trên. Magic !!! hay **hư cấu** 

**Flutter** sử dụng **DART**. Một ngôn ngữ lập trình hướng đối tượng do Google phát triển. **DART** là một static type language nên nó là **AOT** (Ahead of Time), compile xong hết rồi mới chạy. Trong khi đó nó cũng là **JIT** (Just in Time) giống như các dynamic type language. Khi dev thì nó sử dụng  **JIT** để hỗ trợ Hot Load và build release thì dùng AOT để tối ưu hiệu năng như một native code bình thường. Lại magic nữa !!!

Theo doc của Flutter Engine, có tới 4 threads (runners) được sử dụng trong app: **Platform Task Runne**r, **UI Task Runner**, **GPU Task Runner** và **IO Task Runner**. Các threads này độc lập và không share memory với nhau, chúng giao tiếp với nhau thông qua channels... tới đây ai fan golang sẽ hiểu và rất thích pattern này.
