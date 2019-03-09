## git操作备忘录

* 在本地新建分支并推送到远程
````
// 检出分支
git checkout -b test
// 远程仓库中创建一个test分支
git push origin test  
````

* 新建本地仓库并推送到git

 ````
 // 新建本地仓库
 
 // 远程仓库中创建一个新的项目，并拿到路径
 
 // 关联本地与远程仓库
    git remote add origin https://github.com/XXX/XXX
    
 // 上传之前，要先pull一下
    git pull origin master
    
 // 上传
    git push -u origin master   
 ````