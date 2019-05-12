## git操作备忘录

* 在本地新建分支并推送到远程
````
// 检出分支
git checkout -b test
// 远程仓库中创建一个test分支
git push origin test  
或者
git push origin dbg_lichen_star:dbg_lichen_star
````

* 新建本地仓库并推送到git

 ````
 // 新建本地仓库
 
 // 远程仓库中创建一个新的项目，并拿到路径
 
 // 关联本地与远程仓库
    git remote add origin https://github.com/LemonYF/node.git
    
 // 上传之前，要先pull一下
    git pull origin master
    
 // 上传
    git push -u origin master   
 ````
 
 ```
https://api.nike.com/product_feed/threads/v2/?anchor=0&count=50
&filter=marketplace%28CN%29
&filter=language%28zh-Hans%29
&filter=channelId%28010794e5-35fe-4e32-aaff-cd2c74f89d61%29
&filter=exclusiveAccess%28true%2Cfalse%29
&fields=active
&fields=id
&fields=lastFetchTime
&fields=productInfo
&fields=publishedContent.nodes
&fields=publishedContent.properties.coverCard
&fields=publishedContent.properties.productCard
&fields=publishedContent.properties.products
&fields=publishedContent.properties.publish.collections
&fields=publishedContent.properties.relatedThreads
&fields=publishedContent.properties.seo
&fields=publishedContent.properties.threadType
&fields=publishedContent.properties.custom
&fields=publishedContent.properties.title
```