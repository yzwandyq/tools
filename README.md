## Smali/Baksmali Android File in Linux environment
  
反编译/回编译安卓文件 Linux环境操作
----------------------------
# 版本/Version

# 第一版

# 日期：2017-6-7
============================

First：

   $ mkdir ~/Mytools

   $ cd ~/Mytools
   
   $ git clone https://github.com/Waitlan/tools.git

Next:

----------------------------
1. Smali/反编译 jar
   
   EXAMPLE

   $ ~/Mytools/tools/apktool --quiet d -f framework.jar -o framework.jar.out

2. Baksmali/回编译 jar

   EXAMPLE
 
   $ ~/Mytools/tools/apktool --quiet b services.jar.out -o services.jar
   
   回编译这个操作并没有签名，所以修改后手动讲回编译的文件打开将classes.dex替换到原来的jar里覆盖
----------------------------
3. Smali/反编译 apk
   
   EXAMPLE

   $ ~/Mytools/tools/apktool --quiet d -f framework-res.apk -o framework-res

4. Baksmali/回编译 apk

   EXAMPLE
 
   $ ~/Mytools/tools/apktool --quiet b framework-res -o 1framework-res.apk

   回编译这个操作并没有签名，所以修改后手动讲回编译的文件打开将classes.dex/resources.arsc或者res/xml下相关文件替换到原来的apk里覆盖
----------------------------
5. Smali/反编译 classes.dex to out

   EXAMPLE

   $ ~/Mytools/tools/baksmali classes.dex
   
   You will see out directory./你可以看见同目录生成out文件夹

6. Baksmali/回编译 out to out.dex

   EXAMPLE

   $ ~/Mytools/tools/smali out
   
   You will see out.dex./你可以看见生成一个out.dex，手动重命名为classes.dex
----------------------------
7. Install/安装依赖框架
   
     Some机型例如小米有很多资源在其他apk关联，要安装框架才可以反编译/回编译其他apk

      EXAMPLE

       $ ~/Mytools/tools/apktool if framework-res.apk
   
===========================

## 版权所有@Waitlan(曦颜XY)
