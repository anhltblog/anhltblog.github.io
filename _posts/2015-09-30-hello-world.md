---
layout: post
title: Hello World!
categories: [cryptography]
tags: [crypto, transposition cipher]
fullview: true
comments: true
date: 2015-12-16 13:30:00
---

Tớ biết đến Beaver Code từ challenge trên [mysterytwisterc3.org](https://www.mysterytwisterc3.org/images/challenges/mtc3-meier-04-biber-en.pdf). Loại mã hóa này bắt nguồn từ một cuộc thi về khoa học máy tính dành cho học sinh Đức (năm 2010).

###Cách mã hóa

Cách mã hóa rất đơn giản:

Đầu tiên, các khoảng trắng (space) ở plaintext sẽ bị loại bỏ.

Tiếp theo, plaintext được chia thành hai phần: bên trái là các ký tự ở vị trí lẻ, bên phải là các ký tự ở vị trí chẵn.

Cứ tiếp tục chia cho đến khi các phần chỉ còn không quá 2 ký tự.

Cuối cùng, gộp các phần lại theo thứ tự từ trái sang phải.

###Ví dụ

Mã hóa ký tự CRYPTO

![capture](https://cloud.githubusercontent.com/assets/5568988/11834419/d975192c-a3fe-11e5-82c8-f530d99fde77.PNG)

Kết quả, ta được ciphertext là CTYROP. Đơn giản, huh?

###Thử thách

Các bạn hãy giải mã chuỗi ký tự sau: **TTRNEHEORAVNEWESEAABBTREOT**


