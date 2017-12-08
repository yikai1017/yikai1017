---
layout: post
title:  "【深度学习】在Ubuntu16.04下安装OpenCV 3.3"
date: 2017-12-02 16:00:26 +0800
categories: Machinelearning
---

### Contents

[1. OpenCV简介](#opencv)

[2. 步骤一: 下载并安装所有的依赖包](#step1)

[3. 步骤二: 下载OpenCV](#step2)

[4. 步骤三: 编译配置OpenCV](#step3)

[5. 步骤四:安装并测试](#step4)

[6. Reference](#ref)

---

<h3 id="opencv">1. OpenCV 简介</h3>

![image](https://www.learnopencv.com/wp-content/uploads/2017/06/install-opencv-3-on-ubuntu.jpg)

**OpenCV**，即Open Source Computer Vision Library，是一个用于图像处理，分析，CV方面的开源函数库，是由C及C++语言编写的，可以在windows，Linux，mac OSX上面运行。库里面的代码都是经过优化，计算效率很高。OpenCV提供了很多[共享库和模块](https://docs.opencv.org/master/d1/dfb/intro.html#gsc.tab=0)，例如：

- Core functionality，一个核心模块，定义基本的数据结构，包括密集的多维Mat数组，和一些被其他模块调用的基本函数。
- Image Processing，图像处理，包括线性和非线性图像滤波，几何图形转化（重置大小，放射和透视变形，通用基本表格重置映射），色彩空间转换，直方图等


- video，一个影像分析模块，它包括动作判断，背景弱化和目标跟踪算法。
- calib3d，基于多视图的几何算法，平面和立体摄像机校准，对象姿势判断，立体匹配算法，和3D元素的重建。
- features2d，平面特征提取，突出的特征判断，特征描述和对特征描述的对比。
- objdetect，目标和预定义类别实例化的侦查（例如：脸、眼睛、杯子、人、汽车等等）。
- videoio，容易使用的视频采集和视频解码器。

同时，由于计算机视觉与机器学习密不可分，该库也包含了比较常用的一些机器学习算法。或许，很多人知道，图像识别、机器视觉在安防领域有所应用。但，很少有人知道，在航拍图片、街道图片（例如google street view）中，要严重依赖于机器视觉的摄像头标定、图像融合等技术。

目前很多大的公司，研究人员，科技机构共同开发和维护支持OpenCV，这些公司和机构包括，Microsoft，IBM，SONY、Siemens、google、Intel、Standford、MIT、CMU、Cambridge等。

<h3 id="step1">2. 下载并安装所有依赖包</h3>

安装配置:

```linux
$ sudo apt-get install build-essential
```

相关的需求包:

```linux
$ sudo apt-get install cmake git libgtk2.0-dev pkg-config libavcodec-dev libavformat-dev libswscale-dev
```

处理图像所需要的包：

```linux
$ sudo apt-get install python-dev python-numpy libtbb2 libtbb-dev libjpeg-dev libpng-dev libtiff-dev libjasper-dev libdc1394-22-dev # 处理图像所需的包
$ sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev libv4l-dev liblapacke-dev
$ sudo apt-get install libxvidcore-dev libx264-dev # 处理视频所需的包
$ sudo apt-get install libatlas-base-dev gfortran # 优化opencv功能
$ sudo apt-get install ffmpeg
```

