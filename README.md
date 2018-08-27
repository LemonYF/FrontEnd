# FrontEnd学习记录

1.基本样式进行修改时，直接使用原有样式名进行修改，比如 修改input不应当使用 .input 而直接使用input 

2.input有兄弟选择器，用于添加样式 

3.input 利用text-indet改变内文字距边框距离

4.CSS媒体查询可做响应式页面，指定最小显示宽高，另写样式

5.按钮一般还是最好使用input或者a标签

6.修改外部样式未生效时注意检查1.是否经过编译 2.编译的配置文件是否正确 3.是否引用 4.class名称是否正确

7.object = {  name："xxx", sex: "", array:[1, 2, 3, 4]}; 

array=['xx', 'yy', 2, 3]

访问时数组使用索引，对象使用键值

8.使用后端框架做模板页面缺点：1.需要关心后端环境配置，耽误时间 2.使用模板变量的方式安全性不够 3.

9.swiper可以轮播div

10.上传文件为多文件时，数据结构应当是对象内包多个数组 如

var formData = new FormData();
        formData.append("file[]", $("#upload")[0].files);
        
11.跳转页面指定跳转位置使用位置锚点

12.jq添加属性 $.attr()  jq 添加样式 $.addclass()  jq控制是否显示 $.show $.hidden  continue 跳出当前循环  break跳出所有循$.inArray(arr[i],itemArr) 判断数组中是否存在指定值     arr = apply_option.split(','); 字符串改为数组

flex问题学习：

1.flex布局想要控制左右边距的话，给布局包一个固定宽度的body，在此body里面左右贴边，就可以控制中间距离，从而控制左右边距
