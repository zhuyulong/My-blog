##初识Git ——自己对GIT的学习笔记和总结
这几天刚刚开始接触GIT，由最初的发展到最后的完成，他就像是一次蜕变一般。昨天我写了一篇关于GIT的发展史，从VCS到集中式版本控制，再到分布式版本控制，这中间的一步步走的相当的艰辛，今天大家我就通过这几天的学习整理一个我的GIT笔记，让更多喜欢学习GIT的人们去了解它。

 首先，我觉得想学习好GIT的话，我们应该先了解一个网站，Giithub网站。他是一个开源协作的社区，可以达到自己和其他人读或者写项目。我觉得这是一个相当不错的学习网站，它集合着大量优秀的代码和学习资料，当然我们更重要的是对它上面GIT的使用．

一。下面是使用GIT的流程：

   1. 先创建一个空的目录：

       $ mkdir demo

$ pwd
/Users/home/demo

 　　ＰＷＤ显示当前目录。

　2..再在空的目录下创建一个空的文件。　　　　

　　$ touch myblog && cd myblog
　　/Users/home/demo/myblog　
　3.　通过git init命令把这个目录变成Git可以管理的仓库：


　　$ git init
　　Initialized empty Git repository in /Users/home/demo/.git/　　
　Git自动将仓库建好，大家可以看到一个空的仓库（empty Git repository），这是在当前目录下多了一个.git的目录，这个目录是Git跟踪管理版本库的，这个目录里面的文件一般比较重要，所以还是和大家说别去删除或修改它。

  4.　用命令git add告诉Git，将文件添加到仓库：

$ git add myblog
  5.通过git commit告诉Git，把文件提交到仓库：

$ git commit -m "add my blog"
    [master (root-commit) cb926e7] wrote a readme file
    1 file changed, 2 insertions(+)
    create mode 100644 myblog
6.接着通过使用命令git remote add origin git@server-name:path/repo-name.git，进行添加远程库。

7.最后使用命令git push -u origin master第一次推送master分支的所有内容，就这样第一次push基本就完成了。

  二：下面是一些常用的基本命令语句：

     Git 常用命令：

git init myblog           -- 创建本地仓库(repository)，将会在文件夹下创建一个 .git 文件夹，.git 文件夹里存储了所有的版本信息、标记等内容

git remote add origin git@github.com:winter1991/myblog.git
                        -- 把本地仓库和远程仓库关联起来。如果不执行这个命令的话，每次 push 的时候都需要指定远程服务器的地址

git add                  -- 从本地仓库增删，结果将会保存到本机的缓存里面
git rm

git commit -m "备注"     -- 提交，把本机缓存中的内容提交到本机的 HEAD 里面

git push origin master   -- 把本地的 commit(提交) push 到远程服务器上，
origin 也就是之前 git remote add origin 那个命令里面的 origin，
origin 替代了服务器仓库地址：git push git@github.com:winter1991/myblog.git master

git status               -- 查看状态
git add -A               -- 提交全部修改
    如果是我们自己建立仓库代码的话：

 1，git init．

 2，创建你的文件，可以用git status来看状态．

 3,　git add  mywork．

 4,git commit (这里面的commit都是commit自己的本地仓库，并不是传到了远端的git服务器上)

 5,git remote add 缩写  http://带git后缀的url地址 ，不指定默认为origin.

 6，git push -u origin master这里会提示输入用户名和密码，传到远端git仓库上。

三。这个总结的是如何去配置SSHkey:

配置 sshkey ：

  上传代码时使用这个 sshkey 来确认是否有上传权限
   1. 创建本地 ssh ： ssh-keygen -t rsa -C "Github 的注册邮箱"
   2. 在 Github 中添加这个 sshkey ：
       复制  C:\Documents and Settings\Administrator\.ssh\id_rsa.pub 文件中的内容(这个内容可以通过命令行 cd .ssh -> ls -la -> cat id_rsa.pub找到)；
       登录  Github --> Account Setting  --> SSH-KEY --> Add SSH-KEY -->
       最后粘贴id_rsa.pub中的内容；
   3. 验证： ssh -T git@github.com
四。最后是有关GIT的配置：

git config --global user.name "xx"
　-- 配置用户名，上传本地到服务器上的时候，在 Github 上会显示这里配置的上传者信息
git config --global user.email "xxx"
 -- 配置邮箱
