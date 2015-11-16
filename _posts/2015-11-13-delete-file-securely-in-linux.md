---
layout: post
title: Xóa file vĩnh viễn trong Linux
categories: [Linux]
tags: [Linux]
fullview: false
comments: true
date: 2015-11-13 23:00:00
---

Khi bạn xóa đi một thứ gì đó, thì dữ liệu vẫn có thể nằm ở đâu đó trên đĩa cứng. Và rất có thể, một anh chàng đẹp trai (như tớ chẳng hạn) sẽ sử dụng các công cụ recover dữ liệu để lấy lại thứ bạn vừa xóa đi. Nếu sử dụng Linux, thì có lẽ bạn thường dùng lệnh **rm** để xóa dữ liệu, nhưng nếu dùng cách này, dữ liệu vẫn có thể recover lại được. Vậy làm thế nào để xóa triệt để một file, folder trên Linux? Có rất nhiều cách để thực hiện điều này, và sau đây là các công cụ hữu ích mà các bạn có thể sử dụng.

###srm

**srm** là một tool trong secure-delete, có tác dụng xóa file vĩnh viễn.

Để sử dụng **srm**, trước hết chúng ta cần cài đặt secure-delete. Trên Ubuntu, bạn gõ:

```

sudo apt-get install secure-delete

```

Đối với RHEL, Fedora, Centos:

```

sudo yum install secure-delete

```

Lệnh **srm** tương tự như **rm**, tuy nhiên, sau khi xóa file, nó sẽ ghi đè và xóa nhiều lần nhằm gây khó khăn cho việc recover dữ liệu:

```

sudo srm  /home/kid/1.png

```

###Shred

**Shred** xóa file một cách dã man và tạn bạo, với mặc định 25 lần ghi đè liên tiếp. Shred được cài đặt sẵn trong tất cả các distro Linux. Cú pháp lệnh như sau:

```

shred /home/kid/1.png

```

Ngoài ra, bạn có thể tăng số lần ghi đè bằng tùy chọn -n <số lần ghi đè>, ví dụ:

```

shred -n 200 /home/kid/1.png

```

###Wipe

Để cài đặt **wipe** trên Ubuntu, các bạn gõ:

```

sudo aptitude install wipe

```

Đối với Redhat Linux, Centos, Fedora:

```

sudo yum install wipe

```

Sử dụng **wipe** rất đơn giản:

```

wipe filename

```

Đấy là những thứ tớ biết. Còn bây giờ, buồn ngủ rồi, hoy đi nha!

![hihi](https://cloud.githubusercontent.com/assets/5568988/11151870/042bcc94-8a62-11e5-86df-7a62364a3f71.PNG)
