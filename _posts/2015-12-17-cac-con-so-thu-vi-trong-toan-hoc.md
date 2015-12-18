---
layout: post
title: Các con số thú vị trong toán học
categories: [Math]
tags: [Math]
fullview: false
comments: true
date: 2015-12-17 15:37:00
---

Dạo một vòng trên mạng, tớ bắt gặp một bài khá thú vị nói về các con số có tính chất đặc biệt, được đặt tên cũng rất... đặc biệt. Xin nói luôn, tớ không phải là người yêu toán học, bài này được post lên với mục đích làm màu là chính.

<div align="center"><img src="https://cloud.githubusercontent.com/assets/5568988/11865676/247687b0-a4d8-11e5-994e-408c3baed778.PNG"></div>

###1. Cặp số thân thiết

```

Định nghĩa - Cặp số thân thiết (amicable numbers) là cặp số tuân theo quy luật: số này bằng tổng tất cả các ước của số kia trừ chính số đó và ngược lại.

```

Cặp số thân thiết đầu tiên được tìm ra, và cũng được chứng minh là cặp số thân thiết nhỏ nhất, là 220 và 284. Hãy thử phân tích một chút: số 220 ngoài bản thân nó ra, còn có 11 ước số là 1, 2, 4, 5, 10, 11, 20, 44, 55 và 110. Tổng của 11 ước số này vừa đúng bằng 284. Ngược lại, số 284 có 5 ước số ngoài bản thân nó, là 1, 2, 4, 71, 142. Tổng của chúng cũng bằng 220.

Thế kỷ 17, nhà toán học Pháp Fermat tìm ra cặp số thân thiết thứ hai là 17296 và 18416. Cũng thời điểm ấy, một nhà toán học Pháp khác tìm ra cặp số thứ ba là 9363544 và 9437056. Điều khiến người ta kinh ngạc nhất là nhà toán học Thụy Sỹ nổi tiếng Euler vào năm 1750 đã công bố một lúc 60 cặp số thân thiết. Giới hạn toán học được một phen kinh hoàng, họ cho rằng  "Euler đã tìm ra hết cả rồi". Nhưng không ngờ, một thế kỷ sau, một thanh niên nước Ý mới 16 tuổi tên là Bacconi đã công bố một cặp số thân thiết vào năm 1866, nó chỉ lớn hơn 220 và 284 một chút, đó là 1184 và 1210 (đúng là tuổi trẻ tài cao mà).

Đấy là chuyện của ngày xưa, thời nay, bạn cũng có thể tìm ra rất nhiều cặp số thân thiết chỉ với một vài dòng code đơn giản.

###2. Cặp số hứa hôn

Không chỉ dừng lại ở mức ***thân thiết***, tiến thêm một bước nữa, các nhà khoa học bắt đầu định nghĩa ***số hứa hôn***.

```

Định nghĩa - Cặp số hứa hôn (Quasiamicable pair) là hai số nguyên dương sao cho tổng các ước của số này (không tính nó) nhiều hơn số kia đúng 1 đơn vị.

```

Những cặp số hứa hôn đầu tiên được tìm ra là (48, 75), (140, 195), (1050, 1925), (1575, 1648), (2024, 2295), (5775, 6128).

Người ta chứng minh được rằng cặp số hứa hôn luôn gồm 1 số chẵn và 1 số lẻ (1 nam 1 nữa, maybe).

###3. Emirp

Nếu bạn đang tra từ điển tiếng Anh thì chắc sẽ không tìm thấy đâu, vì nó là từ viết ngược của ***Prime***. Hiểu nôm na nó là số nguyên tố ngược.

```

Định nghĩa - Emirp là một số nguyên tố mà sau khi đảo ngược vị trí các chữ số của nó, ta lại được một số nguyên tố khác. Định nghĩa này không bao gồm các số nguyên tố viết xuôi ngược như nhau, chẳng hạn 151 hay 787, cũng không phải số nguyên tố chỉ có một chữ số như 5 hay 7.

```

Những số Emirp đầu tiên được tìm ra là 13, 17, 31, 37, 71, 73, 79, 97, 107, 113, 149, 157,...

###4. Số hoàn hảo

```

Định nghĩa - Số hoàn hảo (Perfect Number) là số có giá trị bằng tổng các ước nguyên dương của nó (tất nhiên là trừ số đó ra).

```

Chẳng hạn, 6 là số hoàn hảo vì: 6 = 1 + 2 + 3.

Về mặt lịch sử, bốn số hoàn hảo đầu tiên (6, 28, 496 và 8128) đã được biết đến từ lâu trong toán học Hy Lạp do nhà toán học Nicomachus tìm ra.

Euclid đã chứng minh rằng \\2^{n-1}(2^n - 1)\\ là một số hoàn hảo khi ***2p - 1*** là số nguyên tố.

Số nguyên tố có dạng ***2n - 1*** được gọi là số nguyên tố Mersenne, lấy theo tên của 17 tu sĩ Marin Mersenne, những người nghiên cứu lý thuyết số và số hoàn hảo. Đến thế kỷ 18, Leonhard Euler đã chứng minh: "Mỗi số nguyên tố Mersenne tạo ra một số hoàn hảo, và ngược lại, mỗi số hoàn hảo tương ứng với một số Mersenne". Kết quả này thường được gọi là định lý Euclid-Euler.

###5. Số mạnh mẽ




