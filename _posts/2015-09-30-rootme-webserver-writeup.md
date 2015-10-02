---
layout: post
title: Root-me Web Server - Write-ups!
categories: [CTF]
tags: [Root-me]
fullview: false
comments: true
---

Bẵng đi một thời gian (khá lâu, khoảng 2 năm) không đụng gì đến CTF, hậu quả là hiện tại tôi thấy kỹ năng về hacking của mình kém ghê gớm (mặc dù trước đó cũng không khá khẩm gì rồi). Nghĩ đến tương lai u ám, đồng nghiệp hắt hủi, bạn bè xa lánh (vì không giỏi thì chúng nó không chơi, còn mình thì vì tự ti mặc cảm nên cũng không chơi nốt), tôi thấy cần phải rèn luyện để tăng skill, tìm lại ánh hào quang mà mình chưa bao giờ có :v

Tôi sẽ bắt đầu với các challenges về _Web Server_.

###1. HTML
**Link:** [http://challenge01.root-me.org/web-serveur/ch1/](http://challenge01.root-me.org/web-serveur/ch1/)

View source code (nhớ kéo sang bên phải). Chả có gì thú vị cả :disappointed:

**Flag:** _nZ^&@q5&sjJHev0_

###2. Weak Password
**Link:** [http://challenge01.root-me.org/web-serveur/ch3/](http://challenge01.root-me.org/web-serveur/ch3/)

username: admin, password: admin --> :sob:

**Flag:** _admin_

###3. User-agent
**Link:** [http://challenge01.root-me.org/web-serveur/ch2/](http://challenge01.root-me.org/web-serveur/ch2/)

Nhìn tên đề bài + gợi ý, đổi user-agent thành admin --> xong.

**Flag:** _rr$Li9%L34qd1AAe27_

###4. Backup file
**Link:** [http://challenge01.root-me.org/web-serveur/ch11/](http://challenge01.root-me.org/web-serveur/ch11/)

Truy cập đến _http://challenge01.root-me.org/web-serveur/ch11/index.php~_

**Flag:** _OCCY9AcNm1tj_

###5. HTTP directory indexing

**Link:** [http://challenge01.root-me.org/web-serveur/ch4/](http://challenge01.root-me.org/web-serveur/ch4/)

Cứ là theo gợi ý thôi: _Ctrl + U_ --> _thấy thư mục admin, thử truy cập thư mục admin_ --> _phát hiện thư mục backup, thử truy cập backup_ --> _thấy file admin.txt_ --> _Flag nằm trong này_

**Flag:** _LINUX_

###6. HTTP Headers

**Link:** [http://challenge01.root-me.org/web-serveur/ch5/](http://challenge01.root-me.org/web-serveur/ch5/)

Dùng LiveHTTP headers xem thử, thấy response trả về có _Header-RootMe-Admin: none_. Thử request lại và thêm trường này vào header thì lòi ra flag.

**Flag:** _HeadersMayBeUseful_

###7. HTTP verb tampering

**Link:** [http://challenge01.root-me.org/web-serveur/ch8/](http://challenge01.root-me.org/web-serveur/ch8/)

Cho đi qua Burp Suite, thay đổi request method thành bất cứ method nào trừ GET và POST. Hết!

**Flag:** _a23e$dme96d3saez$$prap_

###8. Install files

**Link:** [http://challenge01.root-me.org/web-serveur/ch6](http://challenge01.root-me.org/web-serveur/ch6)

View source code, phát hiện đường dẫn /web-serveur/ch6/phpbb/. Truy cập đến thì trằng trơn, chả có gì. Đề bài là Install files và có thêm gợi ý _You know phpBB ?_ --> đi tìm đường dẫn đến file install của phpBB (là _install/install.php_). Flag nằm trong file này.

**Flag:** _karambar_

###9. Improper redirect

**Link:** [http://challenge01.root-me.org/web-serveur/ch32/](http://challenge01.root-me.org/web-serveur/ch32/)

Truy cập đến URL trên thì bị redirect về trang login.php. Dùng addon NoRedirect của FireFox để chặn redirect, sau đó request lại, được flag.

**Flag:** _ExecutionAfterRedirectIsBad_

###10. CRLF

**Link:** [http://challenge01.root-me.org/web-serveur/ch14/](http://challenge01.root-me.org/web-serveur/ch14/)

Bài này yêu cầu bypass form login. Để ý _Authentication log_, có hai dòng _admin failed to authenticate._ và _admin authenticated._. Có thể ngầm hiểu là đăng nhập thất bại và thành công. Sau vài lần thử thất bại, mình thấy log cứ dài ra, toàn là _<username> failed to authenticate_. Ngẫm một lúc, mình suy đoán logic ở đây có thể như sau: sau khi người dùng gửi request lên, server sẽ check thông tin và ghi vào log, sau đó check lại log, nếu có _xxx_

**Flag:** _rFSP&G0p&5uAg1%_

###11. File upload - double extensions

###12. File upload - MIME type

###13. HTTP cookies

###14. Directory traversal

###15. File upload - null byte

###16. PHP filters

###17. PHP register globals

###18. Local File Inclusion

###19. SQL Injection - authentication

###20. SQL Injection - string

###21. LDAP Injection - authentication

###22. NoSQL Injection - authentication

###23. Path Truncation

###24. PHP Serialization

###25. SQL Injection - numeric

###26. SQL Truncation

###27. XML External Entity

###28. XPath Injection - authentication

###29. SQL Injection - Error

###30. SQL Injection - Insert


_..._
