---
layout: post
title: Root-me Network - Write-ups!
categories: [CTF]
tags: [Root-me]
fullview: false
comments: true
---

Tổng hợp writeups Root-me Network :)

###1. FTP - authentication
**Link:** [http://challenge01.root-me.org/reseau/ch1/ch1.pcap](http://challenge01.root-me.org/reseau/ch1/ch1.pcap)

Đọc file pcap lấy flag.

**Flag:** _cdts3500_

###2. TELNET - authentication
**Link:** [http://challenge01.root-me.org/reseau/ch2/ch2.pcap](http://challenge01.root-me.org/reseau/ch2/ch2.pcap)

Tiếp tục đọc file pcap lấy falg.

**Flag:** _user_

###3. ETHERNET - frame
**Link:** [http://www.root-me.org/en/Challenges/Network/ETHERNET-frame](http://www.root-me.org/en/Challenges/Network/ETHERNET-frame)

Đề bài cho một đoạn hex:
```
     00 05 73 a0 00 00 e0 69 95 d8 5a 13 86 dd 60 00
     
     00 00 00 9b 06 40 26 07 53 00 00 60 2a bc 00 00
     
     00 00 ba de c0 de 20 01 41 d0 00 02 42 33 00 00
     
     00 00 00 00 00 04 96 74 00 50 bc ea 7d b8 00 c1
     
     d7 03 80 18 00 e1 cf a0 00 00 01 01 08 0a 09 3e
     
     69 b9 17 a1 7e d3 47 45 54 20 2f 20 48 54 54 50
     
     2f 31 2e 31 0d 0a 41 75 74 68 6f 72 69 7a 61 74
     
     69 6f 6e 3a 20 42 61 73 69 63 20 59 32 39 75 5a
     
     6d 6b 36 5a 47 56 75 64 47 6c 68 62 41 3d 3d 0d
     
     0a 55 73 65 72 2d 41 67 65 6e 74 3a 20 49 6e 73
     
     61 6e 65 42 72 6f 77 73 65 72 0d 0a 48 6f 73 74
     
     3a 20 77 77 77 2e 6d 79 69 70 76 36 2e 6f 72 67
     
     0d 0a 41 63 63 65 70 74 3a 20 2a 2f 2a 0d 0a 0d
     
     0a 
```

Tớ convert sang ASCII thì được:

```
    s  ᩕٚǝ`    ۆ@&S  `*ܠ   ۞^ AРB3       ״ Pݪ}ؠ ⏠  
    >iٗ¾ԇET / HTTP/1.1
    Authorization: Basic Y29uZmk6ZGVudGlhbA==
    User-Agent: InsaneBrowser
    Host: www.myipv6.org
    Accept: */*
```

Decode chuỗi base64 thì ra flag.

**Flag:** _confi:dential_
