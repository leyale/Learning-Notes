
## 概念

**git：** 是一个辅助我们开发的工具，在开发的过程中记录我们每次提交代码的相关内容，比如谁在什么时候修改或者新增了什么功能等等，通过git 可以对我们的代码进行管理，也能借助git 将之前上传的项目克隆到本地
     
**github：**  一个网站，上面有很多的开源项目，可以供我们下载源码之类的，可以作为一个远程仓库，也可以再上面分享一些技术等等


**svn 跟 git 的区别**
两者都是用来处理多人开发的

**svn**采用的是集成式的管理方式
			集成式： 在多人开发一个项目的时候，需要准备一个中央服务器上，每个人在开发的时候都需要先链接上这个中央服务器，如果没有链接上就无法进行开发，要是中央服务器上的话，也需要将里面的数据再做备份，以免丢失之后就没有了
			
**git：** 采用的是分步式
			分步式： ，在每人得电脑上都有，所以开发人员都可以直接在自己的电脑上操作

**如何从一个电脑访问另一台电脑的项目数据**
     可以直接利用github 这个远程仓库，把各自的项目数据上传储存，从一个设备上获取数据，就直接在远程仓库克隆一份到本地就好的
  <br/>
<hr/>

## 获取 Git 仓库
1.  在现有项目或目录下导入所有文件到 Git 中
2. 从一个服务器克隆一个现有的 Git 仓库

### 在现有目录中初始化仓库
1. 找到项目所在目录，使用命令 == git init==
2. 该命令将创建一个名为 .git 的子目录，这个子目录含有你初始化的 Git 仓库中所有的必须文件

### 克隆现有的仓库
作用：可以将某个开源项目克隆到自己本地，比如在github上克隆一个项目
命令： == git clone 克隆地址==   （关于克隆地址，请查看下面的 “用命令行下载  github 中的文件”）
克隆之后： 在当前目录下创建一个克隆下来的目录，里面包含了 .git 文件夹
 <br/>
<hr/>

## 使用

**1. 安装git**
在官网下载就好
		下载之后就可以看到一个github的图标  以及一个git shell
		github是一个可视化的操作
		git shell 是通过命名来操作 （推荐）

**2. 注册登录github**
地址：https://github.com/


**3. 建立仓库**
登录之后  点击页面右上角的加号  就可以看到 New reposition  ,也就是一个仓库
具体操作内容 如下图
![在这里插入图片描述](https://img-blog.csdn.net/20181025115437870?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzQxMDQxOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

<br/>

**4. 建立仓库的细节**
![在这里插入图片描述](https://img-blog.csdn.net/201810251208332?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzQxMDQxOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)



**5. 建立完成**
![在这里插入图片描述](https://img-blog.csdn.net/20181025121030587?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzQxMDQxOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)
<br/>

**6. 用命令行下载  github 中的文件**

1. cd 到你要储存下载文件的位置    
2.  输入命令： ==git clone  url==  （url 地址 在github上，如下图，将这个地址复制过来即可） ![在这里插入图片描述](https://img-blog.csdn.net/2018102512251373?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3dlaXhpbl80MzQxMDQxOQ==/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70)

3. 下载完成
在相应的目录下可以看到 drag （你的仓库名）这个文件夹，点击进去之后就可以看到 .git 以及 README.md 两个文件
.git：  是项目所需要的一些文件之类的，不要改动
 README.md ： 就是我们的项目介绍了，这里支持markdown的语法

4. 设置贡献者（设置有哪些人可以修改 ）
 a. 在命令行 使用 cd 进入到项目所在文件根目录（在这里  就是  cd drag）
 
 b. 设置全局的用户名  命令： ==git config --global user.name " github的用户名 "==
 
c. 设置全局的邮箱  命令： ==git config --global user.email" github所绑定的邮箱 "==

d.查看所设置的邮箱或者用户名 直接输入命令：  ==git config --global user.email  /  git config --global user.name==

e.查看git下的所有配置等等  命令： ==git config --list==
f. 查看 git 下的某一项配置， 命令： ==git config user.email ==


**7.注意事项**
1. 当安装完 Git 应该做的第一件事就是设置你的用户名称与邮件地址。 这样做很重要，因为每一个 Git 的提交都会使用这些信息，并且它会写入到你的每一次提交中，不可更改
2. 关于 ==- -global== 选项：如果使用了 --global 选项，那么该命令只需要运行一次，因为之后无论你在该系统上做任何事情， Git 都会使用那些信息。 当你想针对特定项目使用不同的用户名称与邮件地址时，可以在那个项目目录下运行没有 --global 选项的命令来配置。

**8. 用命令获取相关帮助**
三种可以找到 Git 命令的使用手册的方法：
>1.  $ git help <verb>
>2. $ git <verb> --help
>3. $ man git-<verb>

**9. 获得 config 命令的手册**
>$ git help config
