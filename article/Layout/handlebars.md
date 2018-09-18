##handlebars helper的使用 

1. {{ 函数名称 变量名称 }}其中所有的方法比如each if之类的都可看作是helper，复杂的逻辑可通过自己写helper实现  
2. 变量名称一定要对应的是数据中的变量名，并且每次each时要注意对应的数据是否正确  
3. handlebars和dropload.js结合使用时会有样式的冲突，dropload的加载中样式一直处于div的最顶部而不是最下方
