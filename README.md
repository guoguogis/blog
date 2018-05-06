目录
====
----------
[1、为什么我的网络越来越慢了？](http://blog.guoguogis.gitpress.org/~posts/others/%E6%88%91%E7%9A%84%E7%BD%91%E4%B8%BA%E4%BB%80%E4%B9%88%E8%B6%8A%E6%9D%A5%E8%B6%8A%E6%85%A2%E4%BA%86.md)

[2、前端跨域](http://blog.guoguogis.gitpress.org/~posts/JavaScript/%E5%89%8D%E7%AB%AF%E8%B7%A8%E5%9F%9F.md)

[3、Array数据类型判断](http://blog.guoguogis.gitpress.org/~posts/JavaScript/isArray.md)

[4、PHP与JS时间戳区别](http://blog.guoguogis.gitpress.org/~posts/PHP/PHP%E4%B8%8EJS%E6%97%B6%E9%97%B4%E6%88%B3%E5%8C%BA%E5%88%AB.md)


----------



```flow
st=>start: 浏览器请求
e=>end: 浏览器渲染
op1=>operation: 有缓存
op2=>operation: 从缓存读取(from cache)
op3=>operation: 带If-None-Match向web服务器请求
op4=>operation: 带If-Modified-Since向服务器请求
op5=>operation: 向服务器请求
op6=>operation: 从缓存读取
op7=>operation: 请求响应

cond1=>condition: Cache-Control是否过期?
cond2=>condition: 判断是否有 Last-Modified
cond3=>condition: 判断是否有 Etag?
cond4=>condition: 服务器判断是200?


st->op1->cond1
cond1(no)->op2
op2->e

cond1(yes)->cond3
cond3(no)->cond2
cond2(no)->op5
op5->op7
op7->e

cond3(yes)->op3
op3->cond4
cond4(no)->op6
cond4(yes)->op7
op6->e

op4->cond4

cond2(yes)->op4




op7=>e
```


  


