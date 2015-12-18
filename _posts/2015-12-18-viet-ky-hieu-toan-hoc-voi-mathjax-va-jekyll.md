---
layout: post
title: Viết ký hiệu toán học với MathJax và Jekyll
categories: [Tips & Tricks]
tags: [MathJax, Jekyll]
fullview: false
comments: true
date: 2015-12-18 11:40:00
---

Bạn dùng Jekyll, bài viết của bạn có ký tự toán học, và bạn muốn chúng phải được hiển thị thật đẹp?

như này

$$a^2 + b^2 = c^2$$

như này

$$ \frac{n!}{k!(n-k)!} $$

hay như này

$$\int_0^\infty \mathrm{e}^{-x}\,\mathrm{d}x$$

Ok, đã có MathJax. Sau đây tớ sẽ tóm tắt cách sử dụng MathJax để làm cho blog của bạn thật đẹp, thật lung linh, thật rực rỡ.

###MathJax là cái gì vậy?

MathJax là một thư viện Javascript, giúp hiển thị các ký tự toán học trên browser. Bạn có thể xem chi tiết tại [trang chủ](https://www.mathjax.org/).

###Dùng MathJax với Jekyll dư lào?

#####Cấu hình

* Trong file ```_config.yml```: ```markdown: redcarpet```.

* Để load MathJax, thêm đoạn sau vào file ```default.html``` (trong folder ```layouts```)

```javascript

<script type="text/javascript"
    src="http://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML">
</script>

```

Ok, xong.

#####Một số lưu ý

* viết biểu thức trên cùng một dòng: ```$$...$$```.

* viết biểu thức trên một dòng riêng: ```\\(...\\)```

###Một số ký tự hay sử dụng

Bảng dưới đây mô tả một số ký tự hay sử dụng:

| Symbol               | Script          |
|----------------------|-----------------|
| \\(\alpha\\)         | \alpha          |
| \\(A\\)              | \A              |
| \\(\beta\\)          | \beta           |
| \\(B\\)              | B               |
| \\(\gamma\\)         | \gamma          |
| \\(\Gamma\\)         | \Gamma          |
| \\(\pi\\)         | \pi          |
| \\(\Pi\\)         | \Pi          |
| \\(\phi\\)         | \phi          |
| \\(\Phi\\)         | \Phi          |
| \\(\varphi\\)         | \varphi          |
| \\(\theta\\)         | \theta          |
| \\(k_{n+1}\\)         | k_{n+1}          |
| \\(n^2\\)         | n^2          |
| \\(k_n^2\\)         | k_n^2          |
| \\(\frac{n!}{k!(n-k)!}\\)         | \frac{n!}{k!(n-k)!}          |
| \\(\binom{n}{k}\\)         | \binom{n}{k}          |
| \\(\frac{\frac{x}{1}}{x - y}\\)         | \frac{\frac{x}{1}}{x - y}          |
| \\(^3/_7\\)         | ^3/_7          |
| \\(\sqrt{k}\\)         | \sqrt{k}          |
| \\(\sqrt[n]{k}\\)         | \sqrt[n]{k}          |
| \\(\sum_{i=1}^{10} t_i\\)         | \sum_{i=1}^{10} t_i          |
| \\(\int_0^\infty \mathrm{e}^{-x}\,\mathrm{d}x\\)         | \int_0^\infty \mathrm{e}^{-x}\,\mathrm{d}x          |
| \\(\sum\\)         | \sum          |
| \\(\prod\\)         | \prod          |
| \\(\coprod\\)         | \coprod          |
| \\(\bigoplus\\)         | \bigoplus          |
| \\(\bigotimes\\)         | \bigotimes          |
| \\(\bigodot\\)         | \bigodot          |
| \\(\bigcup\\)         | \bigcup          |
| \\(\bigcap\\)         | \bigcap          |
| \\(\int\\)         | \int          |
| \\(\oint\\)         | \oint          |
| \\(\iint\\)         | \iint          |
| \\(\iiint\\)         | \iiint          |
| \\(\idotsint\\)         | \idotsint          |
| \\(\sum_{\substack{0<i<m\0<j<n}} P(i, j)\\)         | \sum_{\substack{0<i<m\0<j<n}} P(i, j)          |
| \\(\int\limits_a^b\\)         | \int\limits_a^b          |
| \\(a` a^{\prime}\\)         | a` a^{\prime}          |
| \\(a’’\\)         | a’’          |
| \\(\bar{a}\\)         | \bar{a}          |
| \\(\ddot{a}\\)         | \ddot{a}          |
| \\(\overrightarrow{AB}\\)         | \overrightarrow{AB}          |
| \\(\overleftarrow{AB}\\)         | \overleftarrow{AB}          |
| \\(\vec{a}\\)         | \vec{a}          |
| \\(\color{red}x\\)         | \color{red}x          |
| \\(\pm\\)         | \pm          |
| \\(!\\)         | !          |
| \\(\int y\, \mathrm{d}x\\)         | \int y\, \mathrm{d}x          |

OK, that's it. Hi vọng qua bài này, việc viết lách với các ký hiệu toán học của các bạn sẽ dễ dàng hơn ;)
