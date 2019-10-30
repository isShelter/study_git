[TOC]

# git/github 配置公钥



## 一、为什么要配置公钥和私钥

Git使用https协议，每次pull, push都要输入密码，相当的烦。
使用git协议，然后使用ssh密钥。这样可以省去每次都输密码。

公钥我们一般是给服务器的,他们到时候在权限中加入我给的公钥,然后当我从远地仓库中下载项目的时候,我在git clone xxx的时候，那个服务器我通过他的绑定的公钥来匹配我的私钥，这个时候,如果匹配,则就可以正常下载,如果不匹配,则失败.

大多数 Git 服务器都会选择使用 SSH 公钥来进行授权。系统中的每个用户都必须提供一个公钥用于授权，没有的话就要生成一个。



## 二、配置公钥

1. 查看是否已经有了ssh密钥： 如果没有密钥则不会有此文件夹，有则备份删除 （也可以配置多个公钥）

```
$ cd ~/.ssh
```

2. 生成ssh公私钥	 (执行下面命令 [把邮箱地址替换成你github的邮箱地址] ，一路回车即可)

```
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```

![sample](./img/1571414471(1).jpg)

3. 执行上面的命令后，会在 ~/.ssh 文件夹下生成几个文件，id_res 是私钥，id_res.pub 是公钥

![sample](./img/1571413810(1).jpg)

4. 查看公钥 （复制公钥的内容，下面我们会使用到）

   ```
   $ cat id_rsa.pub
   ```

![sample](./img/1571414797(1).jpg)

5. 打开github并登录，点击你的头像选择 【settings】

![sample](./img/1571415058(1).jpg)

6. 选择 【SSH and GPG keys】，再选择 【New SSH key】

   ![sample](./img/1571415248(1).jpg)

7. 给自己的ssh key写一个title，把上面的公钥内容拷贝进去,然后选择 【Add SSH key】

![sample](./img/1571415483(1).jpg)

8. 添加好ssh key后，重新打开【settings】选择【SSH and GPG keys】就能看到你配置好的公钥了

![sample](./img/1571415828(1).jpg)



## 三、使用公钥

1. 复制项目的 公钥地址

![sample](./img/1571416520(1).jpg)

2. 打开git,clone 该项目 (clone 过程中会让我们确认，我们 选择 yes)

```
$ git clone git@github.com:isShelter/study_git.git
```

![sample](./img/1571416919(1).jpg)

3. 如上，我们使用 ssh 地址，就把项目clone到我们本地了



## END

