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

Đề bài cho một đoạn hex. Tớ convert sang ASCII thì thấy có một chuỗi base64: _Y29uZmk6ZGVudGlhbA==_

Decode chuỗi base64 thì ra flag.

**Flag:** _confi:dential_
