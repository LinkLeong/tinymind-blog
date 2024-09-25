---
title: ZimaOS修改磁盘错位问题
date: 2024-09-25T03:09:35.255Z
---

ZimaOS只针对IceWhale的产品进行了适配，如果是其他设备安装ZimaOS会出现磁盘错位问题，这个教程会解决该问题。
## 确定硬盘是否错位
插入新硬盘后首页会收到新硬盘的通知，如图，确认新硬盘的数量后。
![newdisk.webp](https://github.com/LinkLeong/tinymind-blog/blob/main/assets/images/2024-09-25/1727231965056.webp?raw=true)
在Stroage里面确认磁盘的数量是否正确
![20240925-104257.jpeg](https://github.com/LinkLeong/tinymind-blog/blob/main/assets/images/2024-09-25/1727232198886.jpeg?raw=true)
如果数量是对的，那就可以结束该教程了。
## 设置硬盘显示到固定位置
- 查看本地硬盘的编号
执行`lsblk -o name,hctl`
![20240925-105858.jpeg](https://github.com/LinkLeong/tinymind-blog/blob/main/assets/images/2024-09-25/1727233151633.jpeg?raw=true)
- 修改配置
修改/etc/casaos/local-storage.conf中的SataStartNumber值，值为lsblk的最小hctl，修改完后，保存重启机器即可。
![20240925-110855.jpeg](https://github.com/LinkLeong/tinymind-blog/blob/main/assets/images/2024-09-25/1727233756118.jpeg?raw=true)