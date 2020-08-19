# 在码云/GitHub中上传已有项目 #

## 1.配置 ##
	
	在项目目录下，右键打开git命令行
	git config --global user.name 'Nyang-git'
	git config --global user.email '1246568637@qq.com'

## 2.初始化并上传 ##
	
	在项目目录下
	git init   
	git remote add origin 码云仓库地址
	git add .
	git commit -m '描述'
	git push -u origin master

## 3.仓库已有文件在本地VScode编辑后上传码云步骤 ##

	不打开vscode，直接在新文件夹下 
	git init
	git clone 码云仓库地址            #下载仓库文件夹
	用vscode打开下载的仓库文件夹，按Ctrl+~打开 git bash
	修改文件后保存
	git add .
	git commit -m '描述'
	git push -u oringin master

## 4.本地编辑已有仓库，后上传码云步骤 ##

	直接在新文件夹下 
	git init
	git clone 码云仓库地址            #下载仓库文件夹
	打开下载的仓库文件夹，打开git bash
	修改文件后保存
	git add .
	git commit -m '描述'
	git push -u oringin master