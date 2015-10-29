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

###4. Twitter authentication
**Link:** [http://challenge01.root-me.org/reseau/ch3/ch3.pcap](http://challenge01.root-me.org/reseau/ch3/ch3.pcap)

Lại một bài đọc file pcap lấy flag.

**Flag:** _password_

###5. CISCO - password
**Link:** [http://challenge01.root-me.org/reseau/ch15/ch15.txt](http://challenge01.root-me.org/reseau/ch15/ch15.txt)

Sau một hồi Google thần chưởng thì tớ tìm được [ blog này](http://haxcess.com/2008/10/21/cisco-password-recovery/).

Làm theo blog thì cũng được, nhưng vấn đề là tớ không tìm được file wordlist.txt cần thiết. Lại quay lại đọc file cấu hình. Các tài khoản khác (hub, admin, guest) đều có thể dò được password. Các bạn cứ search "crack cisco type 7 password" là ra cả đống tool online :v

Sau khi crack được password của các user trên, tớ thấy chúng đều có tiền tố là **6sK0_**. Thử _6sK0\_enable_ thì ok luôn :D

**Flag:** _6sK0\_enable_

###6. DNS - zone transfert
**Link:** [http://www.root-me.org/en/Challenges/Network/DNS-zone-transfert](http://www.root-me.org/en/Challenges/Network/DNS-zone-transfert)

Tớ sử dụng lệnh _dig_ (trên Linux) để truy vấn đến DNS server.
```
dig @challenge01.root-me.org -p 54011 ch11.challenge01.root-me.org TXT
```

**Flag:** _CBkFRwfNMMtRjHY_

