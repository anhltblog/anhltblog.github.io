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

Bài này yêu cầu bypass form login. Để ý _Authentication log_, có hai dòng _admin failed to authenticate._ và _admin authenticated._. Có thể ngầm hiểu là đăng nhập thất bại và thành công. Sau vài lần thử thất bại, mình thấy log cứ dài ra, toàn là _username failed to authenticate_. Ngẫm một lúc, mình suy đoán logic ở đây có thể như sau: sau khi người dùng gửi request lên, server sẽ check thông tin và ghi vào log, sau đó check lại log, nếu có _xxx authenticated._ thì đưa ra flag. Do đó, mình thử nhập username là _abc authenticated.%0d%0aguest_ --> Done! :D

**Flag:** _rFSP&G0p&5uAg1%_

###11. File upload - double extensions

**Link:** [http://challenge01.root-me.org/web-serveur/ch20/](http://challenge01.root-me.org/web-serveur/ch20/)

Bài này là double extensions, và mục tiêu là upload được file php lên server. Công việc đơn giản chỉ là tạo ra một file php, sau đó lưu dưới dạng .png, chẳng hạn _kid.php.png_, rồi gửi lên server, truy cập đến file vừa upload --> lấy flag.

**Flag:** _PV1OejHY4MxfsC2mHpRz9_

###12. File upload - MIME type

**Link:** [http://challenge01.root-me.org/web-serveur/ch21/](http://challenge01.root-me.org/web-serveur/ch21/)

Tương tự bài bên trên, chỉ có điều, lần này đổi Content-type gửi lên, từ _application/octet-stream_ thành _image/jpeg_.

**Flag:** _UN2YusYPnmwfHFHI5zj3_

###13. HTTP cookies

**Link:** [http://challenge01.root-me.org/web-serveur/ch21/](http://challenge01.root-me.org/web-serveur/ch21/)

Bài này chỉ việc sửa cookie thành _admin_ là xong.

**Flag:** _ml-SYMPA_

###14. Directory traversal

**Link:** [http://challenge01.root-me.org/web-serveur/ch15/ch15.php](http://challenge01.root-me.org/web-serveur/ch15/ch15.php)

Truy cập đến URL trên, click vào một tab, chẳng hạn _actions_.

Để ý đến URL: _http://challenge01.root-me.org/web-serveur/ch15/ch15.php?galerie=actions_

Thử đổi _galerie=./_, mình thấy có một thư mục ẩn là _86hwnX2r_. Thử đổi tiếp _galerie=86hwnX2r_ xem sao. Thấy có file _password.txt_. Hê hê, đọc file này thôi :D

**Flag:** _kcb$!Bx@v4Gs9Ez_

###15. File upload - null byte

**Link:** [http://challenge01.root-me.org/web-serveur/ch22/](http://challenge01.root-me.org/web-serveur/ch22/)

Cái tên nói lên tất cả, chỉ cần sửa tên file thành _kid.php%00.png_ là xong.

**Flag:** _YPNchi2NmTwygr2dgCCF_

###16. PHP filters

**Link:** [http://challenge01.root-me.org/web-serveur/ch12/](http://challenge01.root-me.org/web-serveur/ch12/)

Tớ thấy có 2 link _http://challenge01.root-me.org/web-serveur/ch12/?inc=accueil.php_ và _http://challenge01.root-me.org/web-serveur/ch12/?inc=login.php_. Có vẻ như có LFI chỗ này, thử thay _inc=../_ thì bắn ra lỗi, LFI thật :3

Nhưng vấn đề là đọc file nào bây giờ, chả có gợi ý nào cả. Thôi đi hỏi anh Goócle (có bà chị làm cùng công ty nói hồi bé bà í toàn đọc như thế, hihi): _"PHP filter local file inclusion"_. Thấy ngay một bài blog có tựa đề _"Using php://filter for local file inclusion"_. Hóa ra ta có thể đọc nội dung nằm giữa _<?php_ và _?>_ bằng cách sử dụng _php://filter/convert.base64-encode/resource_ (có từ phiên bản PHP 5.0 trở đi). Quay lại thử đọc file login.php xem dư lào:

```
http://challenge01.root-me.org/web-serveur/ch12/?inc=php://filter/convert.base64-encode/resource=login.php
```

Hê hê, ra một đoạn base64, decode base64 thì lại phát hiện ra một file _config.php_ nữa. Đọc tiếp file này thì ra flag. Hết!

**Flag:** _DAPt9D2mky0APAF_

###17. PHP register globals

**Link:** [http://challenge01.root-me.org/web-serveur/ch17/](http://challenge01.root-me.org/web-serveur/ch17/)

Bài này là PHP register globlas. Tớ đi google trước cho đỡ bỡ ngỡ (_ _!)

Khi register_globals được enabled, PHP sẽ tự động tạo biến global cho tất cả các giá trị truyền qua GET, POST hay COOKIE. Thử tưởng tượng, điều gì sẽ xảy ra nếu server có sử dụng biến _SESSION['xxx'] và tớ lại truyền một biến _SESSION['xxx'] lên server? :v :v :v

Ở đây, có một gợi ý là _"It seems that the developper often leaves backup files around..."_, vậy đi tìm file backup thôi. Sau  một phút mò mẫm thì tớ tìm được file _index.php.bak_. Đây là một phần nội dung của file này:

``` php

if ( isset($_POST["username"]) && isset($_POST["password"]) ){

    if ($_POST["username"]==$username && $_POST["password"]==$password){
	
      print("<h2>Welcome back !</h2>");
	  
      print("To validate the challenge use this password<br/><br/>");
	  
    } else {
	
      print("<h3>Error : no such user/password</h2><br />");
	  
    }
	
}

```

Đến đây, có những 2 cách để đến được đích:

1. Gửi lên hai biến password và hidden_password có giá trị giống nhau.
2. Gửi lên biến _SESSION["logged"]=1.

**Flag:** _NoiQYdpcd5kgNwG_

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
