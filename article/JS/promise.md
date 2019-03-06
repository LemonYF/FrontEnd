# promise
* Promise对象用于异步计算。
* 将异步操作队列化，按照期望的顺序执行并返回符合预期的结果。
* 可以在对象之间传递和操作Promise
* 处理队列
### 异步操作的常见语法
  jquery ajax
```javascript
  $.ajax('http://baidu.com', {
      success: function(res) {
          console.log(res)
      }
  })
  ```
  或者在页面加载完毕后回调
```javascript
$(function() {
  // 回调函数
})
```
### 异步回调问题
嵌套层次很深，难以维护
无法正常使用return 和throw
无法正常检索堆栈信息
多个回调之间难以建立联系

### promise使用
````javascript
new Promise(
    
    // 以下为执行器 executor
    function(resolve, reject) {
      //一段异步操作
      
      resolve(); // 数据处理完成
      
      reject(); // 数据处理出错 
    }
).then(function A() {
    // 成功的下一步
  }, function B() {
    // 失败的下一步
    })
````
* promise是一个代理对象，他和原先要进行的操作并无关系
* 她通过引入一个回调，避免更多的回调

  