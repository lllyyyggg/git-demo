1. 首先在github上面创建一个带README.md的空项目。
2. 将项目pull下来。
	
	可以选择两种方式进行克隆。ssh和https。	
	若是https的方式，直接clone就行。
	若是ssh的方式，进行如下操作。
	
	`ssh-keygen -t rsa -C "your mail address"`
	
	然后将/Users/username/.ssh/下的id_rsa.pub下的内容复制到settings->deploy-keys->add deploy key。
	
	然后`git clone xxx.git`
	
3. 添加文件到暂缓区
	* 	`git add filename`	用于将文件添加到缓冲区。
	* 	`git status` 查看缓冲区状况。
	* 	`git commit -m "xxx"` 提交缓冲区数据到仓库。
	* 	`git push`  会将commit的内容提交到远端仓库。
	* 	`git log` 查看git commit日志。
	* 	`git pull` 从远端拉到本地，并且会强制覆盖本地的文件。和`git fetch -all`一样。
	* 	`git rm filename` 删除本地仓库文件
	* 	`git mv file1 file2` 重命名本地仓库文件
	* 	`git commit -amend` 这次的commit会代替前一次的commit的，一般用于在commit之后发现还有文件忘记添加了，类似于补卡。 
	* 	`git checkout -b mybrach` 切换到其他分支，`git checkout master` 切换到其他分支
	* 	`git reset --hard 序列号` 回退版本
	*  `git branch --all` 查看所有分支。
	*  `git config user.name` 查看当前用户
	*  `git config user.email` 查看当前用户邮箱
	*  `git config --global user.name "lllyyyggg"` 切换用户名 
	*  `git config --global user.email "YOUREMAIL"` 切换用户邮箱
	
4. .gitignore文件。<br>
标示要忽略的文件。*.log表示忽略所有.log结尾的文件。  /hello表示忽略hello目录及其下所有文件的提交。

5. git怎么往远程仓库添加本地仓库。

	```
	git remote add origin https://github.com/lllyyyggg/hello.git
	git push -u origin master
	```
	
6. merge必须切回主分支，然后使用`git merge mybrach`进行merge。
	
7. merge时解决冲突。

	首先编辑冲突文件。然后commit。然后push。
	
	然后干掉mybrach分支。`git branch -d mybrach`。
	
	然后问题解决。

8. 远程删除分支	

	`git push origin --delete mybranch`
	
9. 远程同步自己的分支，并创建pull request。

	* 同步本地自己的分支。
	  `git push origin mybranch:mybranch`
	  
	* 然后到github网站上去创建pull request。

10. 如果在pull的时候报错了。`fatal: refusing to merge unrelated histories`
  
    使用如下命令:`git pull origin master --allow-unrelated-histories`来解决。	
11. 总结开发流程。

	* 克隆项目到本地。
	* 创建自己的分支。
	* 然后将自己的分支同步到github上。
	* 如果自己的分支上开发完成，可以选择`git merge mybranch`。	
	* 如果还没有开发完成，可以直接`git push`。
	* 然后到github上创建自己的pull request。
	* 等待自己的分支被干掉。	
	* ok。
 		



