GIT（gitbash常用操作）
cat XX                                                   查看XX文件内容
git init                                                 将目录变成git可以管理的仓库
git add 文件名                                           添加文件到暂存区
git commit -m '注释'                                     提交文件到仓库
git status                                               是否有未提交的文件
git diff 文件                                            查看更改
git log                                                  查看日志
git log --pretty=oneline                                 查看日志 简洁版
git log --author=提交者 --oneline                        查看默个人提交的历史记录
git reset  –hard HEAD^ ^代表回退的版本 ~100
cat 文件                                                 查看文件内容
git reflog HEAD@{1}                                      获取提交版本号
git branch                                               获取所有分支信息
git branch name                                          创建分支
git checkout –b name                                     创建+切换分支
git checkout master                                      切换当前项目的那个分支
git merge dev                                            合并dev 到当前分支
git branch -d dev                                        删除分支
git stash                                                将当前工作现场隐藏
git stash pop                                            恢复的同时把stash内容也删除了。
git remote/git remote -v                                 要查看远程库的信息/详细信息 
git pull                                                 拉取最新分支的代码
git fetch                                                相当于是从远程获取最新版本到本地，不会自动合并。


git remote add origin https://github.com/tugenhua0707/testgit.git 已有的本地仓库与github关联
git push -u origin master将本地代码推行到远程github  （第一次要用-u 以后不需要）

把本地master分支的最新修改推送到github上了
git push origin master


–no-ff来禁用”Fast forward”模式，即使分支删除他的提交记录还在（git merge –no-ff  -m “注释” dev）


ssh-keygen -t rsa -C "绑定GIT邮箱地址"               设置SSH密钥