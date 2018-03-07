# WHBLEDemo  （OC & Swift）
CoreBluetooth central and peripheral demo with OC/Swift 

(iOS蓝牙中心设备和外设开发,本例中包含Swift版本)

iOS蓝牙开发基础请到这里查阅：**[iOS蓝牙开发介绍](https://remember17.github.io/2017/07/18/iOS%E8%93%9D%E7%89%99%E5%BC%80%E5%8F%91%EF%BC%8C%E4%B8%AD%E5%BF%83%E8%AE%BE%E5%A4%87%E5%92%8C%E5%A4%96%E8%AE%BE%E7%9A%84%E5%AE%9E%E7%8E%B0%EF%BC%8C%E6%9C%89Demo/)**

## 目的

最近公司在做一个iOS蓝牙项目，在开发的过程中简单整理了一些与之相关的基础知识，在这里分享一下。整理包括以下内容：

>1、iOS蓝牙开发的关键词
2、蓝牙的简单介绍
3、CoreBluetooth框架
4、实现iOS蓝牙外设（Demo）
5、实现iOS蓝牙中心设备（Demo）

Demo的运行gif图如下，中心设备可以从外设读取数据，也可以向外设写入数据。外设也可以向中心设备发送数据。
PS：需要使用真机测试。

![蓝牙外设与中心设备之间的数据传输](http://upload-images.jianshu.io/upload_images/3873004-534bd304c4e797e6.gif?imageMogr2/auto-orient/strip)


iOS的蓝牙开发是围绕着CoreBluetooth框架来实现的。
下面先从iOS蓝牙开发的基本概念说起。

## 一、iOS蓝牙开发的关键词

> 中心设备：就是用来扫描周围蓝牙硬件的设备，比如通过你手机的蓝牙来扫描并连接智能手环，这时候你的手机就是中心设备。

> 外设：被扫描的设备。比如当你用手机的蓝牙扫描连接智能手环的时候，智能手环就是外设。

![中心设备和外设](http://upload-images.jianshu.io/upload_images/3873004-a71ce7964e84a2ce.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 广播：就是外设不停的散播蓝牙信号，让中心设备可以扫描到。

![外设广播](http://upload-images.jianshu.io/upload_images/3873004-7ea93e545a2a4ec2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 服务（services）：外设广播和运行的时候会有服务，可以理解成一个功能模块，中心设备可以读取服务。外设可以有多个服务。

> 特征（characteristic）：在服务中的一个单位，一个服务可以有多个特征，特征会有一个value，一般读写的数据就是这个value。

![服务和特征.png](http://upload-images.jianshu.io/upload_images/3873004-444f173afd4f1e86.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


> UUID：区分不同的服务和特征，可以理解为服务和特征的身份证。我们可以用UUID来挑选需要的服务和特征。

**[CoreBluetooth框架 实现iOS蓝牙外设 实现iOS蓝牙中心设备](http://www.jianshu.com/p/38a4c6451d93)**
