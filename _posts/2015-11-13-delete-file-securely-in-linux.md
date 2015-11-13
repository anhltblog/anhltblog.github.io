---
layout: post
title: Xóa file vĩnh viễn trong Linux
categories: [Linux]
tags: [Linux]
fullview: false
comments: true
date: 2015-11-13 17:00:00
---

Khi bạn xóa đi một thứ gì đó, thì dữ liệu vẫn có thể nằm ở đâu đó trên đĩa cứng. Và rất có thể, một anh chàng đẹp trai (như tôi chẳng hạn) sẽ sử dụng các công cụ recover dữ liệu để lấy lại thứ bạn vừa xóa đi. Nếu sử dụng Linux, thì có lẽ bạn thường dùng lệnh **rm** để xóa dữ liệu, nhưng nếu dùng cách này, dữ liệu vẫn có thể recover lại được. Vậy làm thế nào để xóa triệt để một file, folder trên Linux? Có rất nhiều cách để thực hiện điều này, và sau đây là các công cụ hữu ích mà các bạn có thể sử dụng.

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

Lệnh **srm*** tương tự như **rm**, tuy nhiên, sau khi xóa file, nó sẽ ghi đè và xóa nhiều lần nhằm gây khó khăn cho việc recover dữ liệu:

```

sudo srm  /home/kid/1.png

```

###Shred

###dd

###Wipe
