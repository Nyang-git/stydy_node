# linux #

## linux宿主机安装python ##
1.环境

	在Linux命令行中执行
	#apt-get update
	#apt-get install gcc
	#apt-get install g++

2.官网下载安装包
	
	也可使用wegt命令，wegt + 下载网址
	https://www.python.org/downloads/source/
	linux安装包：Download Gzipped source tarball
	Ocen安装包：Download XZ compressed source tarball
	
	
3.安装包放到linux任意目录下，解压
	
	#tar -vxf Python-3.8.4.tar

4.进入解压后的目录

	安装命令，设置安装位置/usr/local/python3（也可自己选择安装位置）
	#./configuer --prefix=/usr/local/python3
	#make
	#make install	 
	安装结束

5.设置软链接

	ln -sf /python3/bin/python3 /usr/bin/python
		   python3的绝对路径     软连接路径

## ARM目标机移植python3 ##

1.准备工具

	Python-3.3.3.tar.bz2
	Python-3.2.2-xcompile.patch

2.解压
	
	#tar -vxf Python-3.3.3.tar.bz2
	#cd Python-3.3.3
	#./configuer
	#make python Parser/pgen
	#mv python hostpython
	#mv Parser/pgen Parser/hostpgen
3.设置环境变量

	#CC=arm-none-linux-gnueabi-gcc
	#CXX=arm-none-linux-gnueabi-g++
	#RANLIB=arm-none-linux-gnueabi-ranlib
	#AR=arm-none-linux-gnueabi-ar
	
	#./configure --host=arm-none-linux-gnueabi --prefix=/home/python-arm
	
	#make HOSTPYTHON=./hostpython HOSTPGEN=./Parser/hostpgen BLDSHARED="arm-none-linux-gnueabi-gcc-shared" CROSS_COMPILE=arm-none-linux-gnueabi-CROSS_COMPILE_TARGET=yes

	编译完成少模块继续安装
	#make install HOSTPYTHON=./hostpython BLDSHARED="arm-none-linux-gnueabi-gcc-shared" CROSS_COMPILE=arm-none-linux-gnueabi-CROSS_COMPILE_TARGET=yes prefix=/home/pythonforarm/python3.8.4/_install

	/home/pythonforarm/python3.8.4/_install路径下有四个目录，表示交叉扁你一完成，复制到arm开发板中
