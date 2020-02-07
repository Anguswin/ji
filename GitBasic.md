## 1/基本配置命令

1. 查看git版本：`git --version`
2. 查看git的配置文件：`cat ~/.gitconfig`，编辑：`vim ~/.gitconfig`
3. 查看用户名：`git config --global user.name`
  `git config --global user.email`
4. 配置SSH：
  （1） 查看是否创建id_rsa.pub文件：`cd ～/.ssh`
  （2）如果未创建则创建id_rsa.pub文件：`$ ssh-keygen -t rsa -C "youremail@example.com"`
  （3）查看SSH私钥：`cat ~/.ssh/id_rsa.pub`
  （4）如果以前配置过SSH，可以用此命令检查连接是否正确：`$ ssh -T git@github.com`

## 2/用git上传本地文件到仓库

1. cd到要上传文件的路径下，如：“cd ~/Users/noodles_bo/Documents/Typora/git使用方法”

2. 初始化，会产生一个.git的文件：“git init”

3. 执行指令将文件添加到本地仓库：二者选其一即可

   ```java
   $ git add .         //添加当前文件夹下的所有文件
   $ git add **.md    //添加当前文件夹下的**.md这个文件
   ```

4. 输入本次的提交说明，准备提交暂存区中的更改的已跟踪文件，单引号内为说明内容：   

    $ git commit -m "layout"  //引号中的内容为对该文件的描述

5. 关联github仓库，在github中新建一个repository，并复制仓库地址：

      //新建一个repository时会出现下面的代码，直接复制即可
      $ git remote add origin https://github.com/Anguswin/gitbasic.git

   如果出现错误：fatal: remote origin already exists，则执行以下语句：

   ​    $ git remote rm origin

   再执行上面的命令：$ git remote add origin https://github.com/Anguswin/gitbasic.git

6. 最后推送到仓库即可：$ git push origin master

   ## 3/ 知识点

   1. push:意思是我们本地的代码有了更新，需要更新到远程来保持同步

   pull：意思是远程代码有了更新，需要把远程代码拉取到本地，保持同步，代码为：git pull origin master

   一般情况下，我们在push之前都会先进行pull操作，这样不容易造成冲突

   2. 如果我们fork了别人的项目，并对其做了修改，想要把我们的代码合并到原始项目中，我们就需要提交一个pull request，让原作者审核。
   3. 提交代码如果本地没有仓库，需要将远程仓库clone到本地。通过clone命令创建的本地仓库，本身就是一个Git仓库，不需要再进行init初始化操作，而且自动关联到远程仓库。我们只需要在这个仓库进行修改，然后commit即可。
   4. 

   