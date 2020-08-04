---
layout: post
title: Container là gì?
date: 2020-07-10 10:00:15
tags: ['docker', 'container']
---

[Container là gì?](https://blogd.net/docker/container-la-gi/)

## Thuật ngữ container

#### Container:

Trong Linux, container là công nghệ ảo hóa hệ điều hành được dùng để gộp applications và các phụ thuộc thành một gói và chạy chúng trong môi trường cô lập. 

#### Container Image:

Container images là tệp tĩnh xác định hệ thống tệp và hành vi của các cấu hình container cụ thể. Container images được dùng làm mẫu để tạo containers.

#### Container Orchestration:

Orchestration là thuật ngữ được sử dụng để mô tả các quy trình và công cụ cần thiết để quản lý lượng lớn container trên nhiều máy chủ. Container orchestration thường kiểm soát tỷ lệ, khả năng chịu lỗi, phân bổ tài nguyên và lập lịch sử dụng nền tảng container. 

#### Container Runtime:

**Container runtime** là thành phần thực sự chạy và quản lý container trên máy chủ. Yêu cầu tối thiểu thường là cung cấp container từ một image nhất định, nhưng nhiều runtimes gộp các chức năng khác như quản lý quy trình, giám sát và quản lý image. Docker bao gồm container runtime trong lệnh docker[/B] của nó, nhưng có nhiều lựa chọn thay thế khác có sẵn cho các trường hợp sử dụng khác nhau. 

#### Linux cgroups:

**Linux cgroups**, hoặc các nhóm kiểm soát, là tính năng kernel kết hợp các quy trình lại với nhau và xác định quyền truy cập của chúng vào tài nguyên.Container trong Linux được triển khai bằng cgroups để quản lý tài nguyên và các quy trình riêng biệt.

#### Linux namespaces:

**Linux namespaces** là tính năng kernel được thiết kế để giới hạn khả năng hiển thị cho một quá trình hoặc cgroup đối với phần còn lại của hệ thống. container trong Linux sử dụng namespaces để giúp cô lập workloads và tài nguyên của chúng khỏi các tiến trình khác đang chạy trên hệ thống.

#### LXC:

LXC là hình thức container hóa Linux có trước Docker và nhiều công nghệ khác trong khi dựa vào nhiều công nghệ kernel tương tự. So với Docker, LXC thường ảo hóa toàn bộ hệ điều hành thay vì chỉ các quy trình cần thiết để chạy application, và có vẻ giống với máy ảo hơn.

#### Virtual Machines (Máy ảo):

Máy ảo hay VM là công nghệ ảo hóa hardware mô phỏng toàn bộ máy tính. Một hệ điều hành đầy đủ được cài đặt trong máy ảo để quản lý các thành phần bên trong và truy cập tài nguyên computing của máy ảo.

#### Virtualization (Ảo hóa):

 Ảo hóa là quá trình tạo, chạy và quản lý môi trường ảo hoặc tài nguyên máy tính. Ảo hóa là cách trừu tượng hóa tài nguyên vật lý và thường được dùng để phân đoạn một nhóm tài nguyên cho các mục đích khác nhau.
