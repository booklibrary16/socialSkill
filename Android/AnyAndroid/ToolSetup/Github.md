[原文地址](https://juejin.im/post/5a2cdfe26fb9a0452936b07f)

$ git co(checkout) -b develop   # → 创建开发分支develop     
$ git push   # → 推送当前分支（develop）到远端仓库     

配置别名：git config --global alias.st status       
------------遵循小批量提交原则------------       
$ git st(status)   # → 查看当前分支工作区、暂存区的工作状态     
$ git diff   # → diff文件的修改（⚠️很重要很重要很重要）      
$ git ci(commit) .   # → 提交本次修改       
------------以上三步使用最频繁-----------      
$ git fetch --all   # → 拉取所有远端的最新代码      
$ git merge origin/develop   # → 如果是多人协作，merge同事的修改到当前分支（先人后己原则）      
$ git merge origin/master   # → 上线之前保证当前分支不落后于远端origin/master，一定要merge远端origin/master到当前分支       
$ git push   # → 推送当前分支到远端仓库       
$ git merge --no-ff origin/develop   # → 同事review code之后管理员合并origin/develop到远端主干origin/master      
--------分--------割--------线--------👉 HEAD：当前commit引用     

$ git branch   # → 查看本地所有的分支      
$ git branch -r # → 查看所有远程的分支      
$ git branch -a # → 查看所有远程分支和本地分支       
$ git branch -d <branchname> # → 删除本地branchname分       
$ git branch -m brancholdname  branchnewname # → 重命名分支        
  $ git branch <branchname> # → 创建branchname分支      
  $ git checkout <branchname> # → 切换分支到branchname       
  $ git checkout -b <branchname> # → 等同于执行上两步，即创建新的分支并切换到该分支       
  $ git checkout -- xx/xx # → 回滚单个文件        
  $ git pull origin master:master # → 将远程origin主机的master分支合并到当前master分支,冒号后面的部分表示当前本地所在的分支       
  $ git pull origin master --allow-unrelated-histories   # → 允许合并两个不同项目的历史记录      
  $ git push origin -d <branchname>   # → 删除远程branchname分支      
  $ git fetch --p   # → 更新分支$ git status # → 查看本地工作区、暂存区文件的修改状态     
  $ git add xx # → 把xx文件添加到暂存区去      
  $ git commit -m ' '  # → 提交文件 -m 后面的是注释(不建议使用👎)     
  $ git commit -am(-a -m) # → 提交所有的修改，等同于上两步(不建议使用👎)     
  $ git commit ./xx   # → 等同于git add ./xx + git commit（建议使用👍）      

