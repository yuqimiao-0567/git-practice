#学习资料来源以及相关链接
  GitHub官方文档:https://docs.github.com/zh
  Git官方文档:https://git-scm.com/doc
  菜鸟教程-Git教程:https://www.runoob.com/git/git-tutorial.html
#实践流程（如安装、配置、使用过程）
  安装:访问 https://git-scm.com 下载安装包，默认选项安装即可
  配置:
  #设置用户名和邮箱
  git config --global user.name "*******"
  git config --global user.email "********"
  使用过程:
  
    $ cd /D/GitLearning
    
    $ git status
    On branch master
    Changes to be committed:
    (use "git restore --staged <file>..." to unstage)
        modified:   test.py
        
    $ git add .
    
    $ git commit -m "第二次提交"
    
    [master 5ce2466] 第二次提交
     1 file changed, 1 insertion(+), 1 deletion(-)
     
    $ git status
    On branch master
    nothing to commit, working tree clean
    
    $ git add README.md
    
    $ git commit -m "第三次提交"
    [master 53c90c1] 第三次提交
     1 file changed, 0 insertions(+), 0 deletions(-)
     create mode 100644 README.md
     
    $ git log --oneline
    53c90c1 (HEAD -> master) 第三次提交
    5ce2466 第二次提交
    92235b9 第一次提交
    
    $ git remote add origin https://github.com/yuqimiao-0567/git-practice.git
    
    $ git push -u origin main
    branch 'main' set up to track 'origin/main'.
    Everything up-to-date
    
    $ ls
    README.md  test.py  《l蓝桥杯算法入门》读书笔记.txt
    
    $ git add .
    
    $ git commit -m "第四次提交:上传读书笔记"
    [main 1c7e3f4] 第四次提交:上传读书笔记
     1 file changed, 21 insertions(+)
     create mode 100644 "\343\200\212l\350\223\235\346\241\245\346\235\257\347\256\227\346\263\225\345\205\245\351\227\250\343\200\213\350\257\273\344\271\246\347\254\224\350\256\260.txt"
    
    $ git push
    Enumerating objects: 4, done.
    Counting objects: 100% (4/4), done.
    Delta compression using up to 24 threads
    Compressing objects: 100% (3/3), done.
    Writing objects: 100% (3/3), 3.66 KiB | 3.66 MiB/s, done.
    Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
    To https://github.com/yuqimiao-0567/git-practice.git
       53c90c1..1c7e3f4  main -> main
    
    $ git log --oneline
    1c7e3f4 (HEAD -> main, origin/main) 第四次提交:上传读书笔记
    53c90c1 第三次提交
    5ce2466 第二次提交
    92235b9 第一次提交
    
#遇到的问题及解决方法
  1.问题:  安装Git后命令行无法识别git命令
    解决方案:   手动添加环境变量
  2.问题:  git add添加了不该添加的文件
    解决方案:  撤销所有暂存区的文件 git reset
  3.问题:刚提交完发现漏掉了文件或写错了提交信息
    解决方案: 使用git commit --amend修改上一次提交
  4.问题: 想要回到之前某个版本看看，之后再回来
    解决方案: 先用git log找到目标commit的ID
              git log --oneline

              切换到目标commit
              git checkout 版本号

              回到原来的分支
              git checkout main
#Git学习心得
  掌握了Git的基本命令:add、commit、push、log
  理解了三个区域:工作区 → 暂存区 → 仓库
  学会了在GitHub上创建仓库并推送代码
