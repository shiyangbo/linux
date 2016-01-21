# linux.1.入门
## 几个概念，同义词
命令 / 程序 / 二进制文件 / 二进制程序代码 / 一个exe / 一个软件    
// 命令是特殊的程序：由shell(如bash)自带一些，由linux内核提供一些，由用户自定义一些
## 常用软件
[网址1](http://www.jianshu.com/p/4adbfd83b29f)  
[网址2](http://linux.linuxidc.com/pub/)，linux公社，用户名和密码：www.linuxidc.com  
## 安装系统
[安装archlinux](https://wiki.archlinux.org/index.php/Beginners%27_guide "官方")  
[安装debian及ubuntu](http://blog.csdn.net/uther542/article/details/8806865)  
[安装centos](http://blog.sina.com.cn/s/blog_86e874d30101e3d8.html)  

详细点，当安装ubuntu时，  
title Install Ubuntu 10.10   
root (hd0,0)  
kernel (hd0,0)/vmlinuz boot=casper iso-scan/filename=/xxx.iso ro quiet splash locale=zh_CN.UTF-8  
initrd (hd0,0)/initrd.lz

// 注意事项

1. 进grub先取消挂载：sudo umount –l /isodevice [详细参考](http://www.360doc.com/content/11/0506/22/6110614_114908124.shtml)  
2. 分区时看不到windows分区 [详细参考](http://forum.ubuntu.org.cn/viewtopic.php?f=77&t=190435 "很精彩")  

    即消除GPT分区表 [进一步参考](http://forum.ubuntu.org.cn/viewtopic.php?t=442575)  

3. 与window7构成双系统时，时钟不同步问题

    概念术语：一个本地计算机的时间 / bios时间 / CMOS时间 / 系统硬件时间 / 系统时钟 / systemclock / 硬件时钟 / 实时时钟RTC  
    概念术语：一个操作系统的时间 / 本地时间 / localtime / 系统时钟 / 软件时间  
    linux系统认为：自己的localtime != bios时间 (UTC策略)  
    mac系统认为：自己的localtime != bios时间 (UTC策略)  
    windows系统认为：自己的localtime == bios时间 (无策略)
    
    解决windows和linux时间不一致的方法有2种：
    1. 设置Windows采用UTC策略 (推荐)
    
        略
    
    2. 设置linux取消UTC策略 (不推荐)
    
        ubuntu发行版本
        
            /etc/default/rcS  # 相关配置文件。
        
        centos发行版本
        
            略。
    
    // 以上两种方式，修改后重启电脑生效  
    // 网上作者注：最好两种方法都设置，我原本只设置一种发现，还是不行，最后两种方法都设置就可以了。  
    // UTC策略：利用GMT / 格林尼治平时，进行世界各地的时间的换算。  
    // 更简单的定义：一个（GMT到localtime）的映射。  
    // 最简单的定义：不要去管它！抛弃一切把简单东西复杂化的狗屁概念。当然，我们承认UTC策略应该是第一优先选择，都怪windows系统不用它，要不然三大操作系统的时钟默认设置就都统一了。  
