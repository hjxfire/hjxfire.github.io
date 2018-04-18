---
layout: post
title:  "Java Swing的不同风格选择"
categories: Java
tags:  Java
author: hjxfire
---

* content
{:toc}

```
    UIManager.setLookAndFeel("com.sun.java.swing.plaf.nimbus.NimbusLookAndFeel");//Nimbus风格,新出来的外观,jdk6 update10版本以后的才会出现 
            //UIManager.setLookAndFeel(UIManager.getSystemLookAndFeelClassName());//当前系统风格 
            //UIManager.setLookAndFeel("com.sun.java.swing.plaf.motif.MotifLookAndFeel");//Motif风格,外观接近windows经典,较为宽大,不是黑灰主色,而是蓝黑 
            //UIManager.setLookAndFeel(UIManager.getCrossPlatformLookAndFeelClassName());//跨平台的Java界面风格 
            //UIManager.setLookAndFeel("com.sun.java.swing.plaf.windows.WindowsLookAndFeel");//windows风格 
            //UIManager.setLookAndFeel("javax.swing.plaf.windows.WindowsLookAndFeel");//windows风格 
            //UIManager.setLookAndFeel("javax.swing.plaf.metal.MetalLookAndFeel");//java风格 
            //UIManager.setLookAndFeel("com.apple.mrj.swing.MacLookAndFeel");//暂时未知
```