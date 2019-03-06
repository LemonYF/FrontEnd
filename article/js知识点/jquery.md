
## 1.上传文件为多文件时，数据结构应当是对象内包多个数组 如
```javascript
    var formData = new FormData();
    formData.append("file[]", $("#upload")[0].files)
```
## 2.jq知识点
* 添加属性$.attr()  jq 添加样式 $.addclass()  
* jq控制是否显示 $.show $.hidden
* continue 跳出当前循环  break跳出所有循环
* $.inArray(arr[i],itemArr) 判断数组中是否存在指定值     
* arr = apply_option.split(','); 字符串改为数组  
## 3. input输入框

* input中onchange只有失去焦点时才会生效，oninput可以实时生效，但是只有原生JS可以使用，JQ中需要绑定方法
```javascript
  $('#search').bind('input propertychange', function() {
          console.log(111)
      });
```