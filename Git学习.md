# Git

## Git概述

Git是一个免费的、开源的**分布式版本控制系统**，可以快速高效地处理从小型到大型的各种项目。具有**廉价的本地库**，**方便的暂存区域**和**多个工作流分支**等特性。

### 版本控制

版本控制是一种**记录文件内容变化**，以便将来**查阅特定版本修订情况**的系统。从而让用户能够**查看历史版本**，**方便版本切换**。

#### 版本控制工具

+ 集中式版本控制工具

  

+ 分布式版本控制工具



## Git下载

### 具体步骤

1. ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905165445703.png)
2. ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905165555728.png)
3. ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905165635643.png)



## Git常用命令

+ 设置用户签名

  用户签名是用来识别客户的标识，必须设置用户签名才能正常使用Git。

  设置用户签名

  `git config --global user.name LuckyE `

  设置用户邮箱

  `git config --global user.email llb1120@outlook.com `

+ 初始化本地库

  只有初始化本地库后，Git才可以对该库进行管理。

  初始化成功后会出现隐藏文件（.git）**不能修改**

  `git init `

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905193856622.png)

  初始化成功。

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905194048259.png)

+ 查看本地库

  `git status`

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905195803874.png)

  + 新增文件

    `vim hello.txt`创建一个新文件，按esc进入编辑模式，按i键进入插入模式。按shift+;键再输入wq保存文件。

  新创建文件后：

  显示hello.txt是**未被追踪**的文件。

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905195857551.png)

+ 添加暂存区

  `git add hello.txt`

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905200624350.png)

  `git rm --cached hello.txt`删除文件，删除的只是暂存区的文件，本地文件（即工作区）并未删除

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905201030919.png)

+ 提交本地库，形成历史版本

  `git commit -m"日志信息" hello.txe`

  日志信息必须带上。

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905201748481.png)

  添加到本地库成功后会得到版本号（图中红色方框）

  + 查看提交信息

    ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905201924688.png)

+ 修改文件

  `vim hello.txt`修改文件 模拟第二次提交文件

  修改后：

  ![image-20220905203842643](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905203842643.png)

  第二次提交之后，指针指向第二次提交文件处。

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905203945716.png)

+ 查看历史版本

  `git reflog`简略

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905204405073.png)

  `git log`详细

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905204423837.png)

+ 历史穿梭

  `git reset --hard 版本号`

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905204726245.png)

  可以看到指针已经指向第一次提交的文件

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905204812424.png)

  显示第一次提交的文件。

  历史穿梭底层实现其实就是**head指针的移动**。

  

## Git分支

### 常用Git分支操作

+ 查看分支

  `git branch -v`

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905210523667.png)

  当前只有一个分支。

+ 创建分支

  `git branch hot-fix `

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905210707950.png)

  当前分支仍是master。

+ 切换分支

  `git checkout hot-fix`

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905211157432.png)

+ 修改分支

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905211635847.png)

+ 合并分支

  `git merge hot-fix`表示将hot-fix合并到当前分支master

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220905211927532.png)

  该情况是正常合并。

  合并冲突：两个分支在同一个文件同一个位置产生了两个完全不一样的修改，Git无法替我们决定哪一个修改，只能人为指定。

  

## GitHub

### GitHub操作

+ 创建远程库

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906191041999.png)

  获取https地址

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906191146731.png)

  + 创建别名

    `git remote -v`查看别名

    `git remote add 别名 项目地址`创建别名

    ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906191621197.png)

    会创建两个别名，一个用于**拉取**，一个用于**推送**。

+ 推送本地库到远程库

  推送的**最小单位**是**分支**！！！

  ` git push git-demo master`

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906193233428.png)

  推送成功！

+ 拉取远程库到本地库

  拉取的**最小单位**同样是**分支**！！！

  `git pull git-demo master`

  保证本地库=远程库。

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906194453513.png)

+ 克隆远程库到本地

  `git clone 地址链接`

  clone完成以下操作：

  + 拉取代码
  + 初始化本地仓库
  + 创建别名（默认为origin）

  

### GitHub团队内协作

+ 添加库成员

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906195557329.png)

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906195644029.png)

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906195724206.png)

  拉取操作和推送操作与前文一致。

  

### GitHub跨团队协作

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906200345867.png)

Fork代码

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906200638793.png)

发起pull requests



### GitHub SSH免密登录

生成SHH密钥

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906203220379.png)

id_rsa.pub为公钥。

获取公钥

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906203413932.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906203643004.png)

添加公钥

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906203830473.png)



## IDEA集成GitHub

### 配置忽略文件

```
# Compiled class file
*.class

# Log file
*.log

# BlueJ files
*.ctxt

# Mobile Tools for Java (J2ME)
.mtj.tmp/# Package Files #
*.jar
*.war
*.nar
*.ear
*.zip
*.tar.gz
*.rar

hs_err_pid*

.classpath
.project
.settings
target
.idea
*.iml
```

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906212952409.png)

### 定位Git程序

打开Idea设置

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906214120145.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906214346521.png)

### 初始化

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220906214810293.png)

### 添加暂存区

+ 方法一

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907162232697.png)

+ 方法二

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907162511588.png)

+ 方法三

  快捷键Ctrl+Shift+A

+ 方法四 整个工程一起添加

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907162924570.png)

### 提交本地库

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907163145243.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907163355976.png)

### 切换版本

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907163833073.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907163846943.png)

#### 查看历史版本、版本号

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907164241537.png)

#### 切换版本

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907164404924.png)

代码发生变化。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907164449273.png)

### 创建分支

+ 方法一

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907165232749.png)

+ 方法二

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907165259584.png)

### 切换分支

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907165446536.png)

### 合并分支

#### 正常合并

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907165937716.png)

合并成功！

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907170002927.png)

#### 冲突合并

两个分支同一个文件同时修改

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907170545624.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907170627729.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907170826970.png)

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907170819195.png)

成功合并！

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220907170911725.png)



## IDEA整合GitHub

### 添加GitHub账号

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908162118293.png)

点击Log In via GitHub可以直接跳到网页验证添加GitHub账号。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908162312590.png)

添加成功！

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908162443398.png)

### 分享项目到GitHub

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908162826682.png)

Repository name：仓库名字

Remote：仓库别名（一般与仓库名一致）

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908162908118.png)

成功分享！

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908163046937.png)

### 推送本地库到远程库

先commit到本地库

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908163602609.png)

push本地库到远程库

+ 方法一

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908163905264.png)

+ 方法二

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908163911515.png)

  该方法默认使用https协议，容易受网速影响。

  一般使用SSH免密登录协议。

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908164955053.png)

  推送成功！

  ![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220908164932053.png)

**注意！！！**

发起push时，如果本地库版本跟远程库版本不一致的话，Git是会拒绝Git操作的。所以每次修改代码之前都要把远程库的代码pull到本地库中。

### 拉取远程库到本地库

当发现GitHub版本与本地库版本不同时，需要pull最新版本到本地库。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220909155428802.png)

推荐使用ssh免密登录进行拉取。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220909155510031.png)

### 克隆远程库到本地库

点击Get from VCS

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220909155833034.png)

使用SSH免密登录clone代码。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220909160159669.png)

绑定了GitHub账号后，也可以直接查询账号中的仓库进行clone。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220909160303830.png)

clone成功。

![](https://xingqiu-tuchuang-1256524210.cos.ap-shanghai.myqcloud.com/54245/image-20220909160440889.png)



