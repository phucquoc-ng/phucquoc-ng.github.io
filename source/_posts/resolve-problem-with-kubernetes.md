---
layout: post
title: Kubernetes giải quyết được vấn đề gì?
date: 2020-07-09 10:56:51
tags: ['kubernetes', 'docker']
---

Vấn đề hiện nay:

> Vấn đề đặt ra, cả ngàn docker container thì có thằng lúc chạy lúc không, lúc overload lúc underload, ai quản lý đống container này.

Tưởng tượng, 1 ngày nào đó cái app của ta được xây dựng xong, đi vào hoạt động, trở nên lớn mạnh và có tới hàng triệu người dùng. Vậy thì khi đó, làm sao để ta xử lý được 1 cái hệ thống với hàng triệu request trong 1 phút như thế? Làm sao để xây dựng 1 cái app có thể dễ dàng scale được ?
