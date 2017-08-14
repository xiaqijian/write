github是一根很好的管理代码的工具

## 1. 如何建立建立
#### 1.1 绑定用户
这个步骤是将我们本地的电脑和github账号进行绑定

在打开的GIt Bash中输入以下命令（用户和邮箱为你github注册的账号和邮箱）
```
$ git config --global user.name "github用户名称"
$ git config --global user.email "github注册时的邮箱"
```
![img](http://upload-images.jianshu.io/upload_images/3067059-f2c6c88dca3cb4f1.png?imageMogr2/auto-orient/strip%7CimageView2/2)

### 1.2 生成ssh

ssh有什么作用  [ssh有什么作用](https://segmentfault.com/q/1010000000118744)

### 1.3 检查是否有ssh
```
$ cd ~/,ssh
$ ls
```
如果发现有里面有文件，则已经生成了

#### 如果没有密钥，则通过下面的方式
```
$ ssh-keygen -t rsa -C "注册github的邮箱"
```
生成，生成过程中一路按3次回车键就好了。（默认路径，默认没有密码登录）
生成成功后，去对应目录C:\Users\hyt.ssh里（hyt为电脑用户名，每个人不同）用记事本打开id_rsa.pub，得到ssh key公钥。

![img](http://upload-images.jianshu.io/upload_images/3067059-ef6cb51d5ad31445.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 1.4 github设置

![img](http://upload-images.jianshu.io/upload_images/3067059-1aba5aba10165470.gif?imageMogr2/auto-orient/strip)

接着将id_rsa.pub文件中key粘贴到此，最后Add key生成密钥吧。

## 2, 上传本地文件

```
// 第一步
$ git init

// 第二步
$ git add .

// 第三步
$ git commit -m "提交文件"

// 第四步

$ git remote add origin https://github.com/仓库地址/text.git

// 第五步
$ git push -u origin master




```

## 3. 更新github
### 3.1 git status
```
$ git status 
```
这个可以查看，本地和github有哪些是先得文件，然后进行相应的文件添加

### 3.2 git add 新文件.html
```
$ git add 新文件.html
$ git commit -m  "更新log日志"
```
### 3.3 git push
```
$ git push // 将新的文件推送到github
```
如果发现github有你本地没有的文件，你先要进行`git pull`

### 总结
```
// 第一步
$  git status

// 第二步
$ git add 新文件.html

// 第三步
$ git commit -m "更新日志"

// 第四步
$ git push





```





