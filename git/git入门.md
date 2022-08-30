# Git入门到入门

## 一些碎碎念

为什么突然会想到讲这个，起初来看是我刚入职的时候就开始用这个样的一个工具，因为团队的整体相对来说会比较大，大约是在20人左右，所以有很多的时候并不是提交推送的一些场景相比与SVN，Git更多的优势是在在于，整个团队的一些合作可自定义性，会更大一些，当然，这也带来一了一些挑战。在不长的行业工作中，git也占用了我不少的时间，包括解决了一些较为复杂的问题，或者是针对整个团队特定的开发流程，定制一些gitflow，有的时候还有一些心得，那么，接下来，我将把这些东西总结下来分享出去，内容不深，但是希望能够给你一些关键时候能用到的一些小技巧。

## 入门

### 环境要求与安装

这个你要看吗？
正在施工中

### 初始化你的第一个仓库
#### 适合用在第一次初始话仓库的指令
那么我们首先来看这个指令
```
git init
```
在这里我们首先找一个空文件夹来初始化一个文件。右键选择git bashhere

![打开git bash](./ImageSource/OpenBash.png)


输入 git init 然后回车，这样我们就成功创建了一个git本地仓库

![init success](./ImageSource/initSuccess.png)

那么在创建了本地仓库以后，可以正常的将代码进行版本管理了，但是还不能与远程仓库能够正常进行链接，这个我们稍后在说

#### 适合用于已经再存的仓库想要下载到本地的指令

```
git clone
```

那么或许，当在集体编码的时候，已经有了一个正在使用的仓库了，那么这个时候就需要使用 clone 命令了。一般这个时候会有一个远程的网页地址需要去访问，我们拿git hub 来进行演示，同等还有gittee ，gitlab 等远程仓库系统，这个我们就不一一展示了。
首先登陆git hub 选择一个正在使用的仓库。

![REPO](./ImageSource/github-repo.png)

其实在这里可以看到三种 clone 代码的方式，
- HTTPS
- SSH
- Github CLI
比较经常用 HTTPS 和 SSH 方式 ，第三种是github 特有的，这个跳过
#### HTTPS
HTTPS的克隆方式非常的简单，可以直接使用指令 
```bash
git clone https://github.com/nanjolono/git-practice.git
```
![cloneForHttps](./ImageSource/cloneHttps.png)

注：如果是私有仓库，会提示你需要输入账号密码，这个是一般是登录网页系统的时候用到的账号密码。
但是这里其实还有一种其他的方式（不推荐使用）
```bash
git clone https://username:password@github.com/nanjolono/git-practice.git
```
那么上述的这个指令是可以将你的账号密码都写入到url中，可以做到clone的时候不需要输入账号密码，但是如果是http协议的仓库，你的账号密码也同样的被暴露了出去。安全性较差
那么http的从远程仓库clone代码的方式，我们已经演示完毕了。在http的协议中，使用起来比较简单，只需要输入账号密码就可以完成代码clone，但是换种形式来说，如果你的密码是定期更改而且这个定期的期限比较短的话，就会需要经常修改密码。那么就要介绍接下来方法了。
#### SSH
SSH clone 代码的方式主要是在电脑上生成一对可以进行ssh协议的公私钥，那么这种认证方式只认机器，无论账号密码如何更换，也不妨碍代码的提交推送。

1. 初始化SSH Key

执行命令

```bash
ssh-keygen -t rsa
```
   ![keyGen](./ImageSource/keyGen.png)
一直输入回车直接在~/.ssh/下生成key
在执行cd 命令切换到公私钥所在的路径下
```bash
cd ~/.ssh/
```
使用cat命令查看生成的公钥
```bash
cat id_rsa.pub
```
复制输出的文字

![pubKey](./ImageSource/pubKey.png)

2. 添加Key
登录github后，选择设置,添加ssh-key
![setPubKey](./ImageSource/addSSHKey.png)
将titile写入你的电脑名称（方便记忆的设备名称就可以）
将复制的PubKey粘贴到Key框中，点击Add SSH Key就可以
![addAhtuKey](./ImageSource/addAuthKey.png)
3. 代码Clone
```bash
git clone git@github.com:nanjolono/git-practice.git
```
无需密码可以下载代码

### 将你的修改推送到远程仓库中

### 获取新的代码

### 后悔药

### 合作开发 merge

### log

### status 


