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

###7. IP - Time To Live
**Link:** [http://challenge01.root-me.org/reseau/ch7/ch7.pcap](http://challenge01.root-me.org/reseau/ch7/ch7.pcap)

Nhiệm vụ ở bài này đơn giản chỉ là đọc file pcap, dòm TTL. Đó chính là flag :D

**Flag:** _13_

###8. LDAP - null bind
**Link:** [http://www.root-me.org/en/Challenges/Network/LDAP-null-bind](http://www.root-me.org/en/Challenges/Network/LDAP-null-bind)

Bài này kết hợp khai thác LDAP null bind và null base.

Sử dụng _ldapsearch_ (trên Linux):
```

ldapsearch -x -h challenge01.root-me.org -p 54013 -b "ou=anonymous,dc=challenge01,dc=root-me,dc=org" "(objectclass=*)" "*" +

```

**Flag:** _sabu@anonops.org_

###9. SIP - authentication
**Link:** [http://challenge01.root-me.org/reseau/ch4/ch4.txt](http://challenge01.root-me.org/reseau/ch4/ch4.txt)

Đọc file txt ra luôn flag. Mất vui :(

**Flag:** _1234_

###10. ETHERNET - Patched transmission
**Link:** [http://www.root-me.org/en/Challenges/Network/ETHERNET-Patched-transmission](http://www.root-me.org/en/Challenges/Network/ETHERNET-Patched-transmission)

Đề bài cho 4 frame. Tớ sử dụng tool _text2pcap_ (có sẵn khi cài wireshark) để tạo file pcap từ file text chứa dữ liệu đề cho. Sau đó, dùng wireshark để xem thì phát hiện hai gói tin ping request 1 và 3 bị hỏng, chỉ có gói thứ 2 là đúng --> gói ping reply cần phục hồi chính là phản hồi của gói 2. Loay hoay một hồi thì cũng ra flag :v

**Flag:** _f9f781003afadab00b81_

