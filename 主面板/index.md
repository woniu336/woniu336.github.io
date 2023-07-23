# 

#### 日记
```dataview
table title AS "标题",date AS "创建时间"
from "日记"
where draft=true
sort date desc
```

#### 草稿箱
```dataview
table title AS "标题",date AS "创建时间"
from "post"
where draft=true
sort date desc
```

### 已发布
```dataview
table title AS "标题",date AS "创建时间"
from "posts"
where draft=false
sort date desc
```









---

> 作者: [woniu336](https://github.com/woniu336)  
> URL: https://99bilibili.eu.org/%E4%B8%BB%E9%9D%A2%E6%9D%BF/  

