# 删除本地文件后 Git从远程仓库重新获取
	git checkout master 
	git reset --hard

	#git 强行pull并覆盖本地文件

	git fetch --all  
	git reset --hard origin/master 
	git pull

