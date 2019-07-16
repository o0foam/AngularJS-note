过滤器可以使用一个管道字符 | 添加到表达式和指令中。

# AngularJS 过滤器

AngularJS 过滤器可用于转换数据:
|过滤器|描述|
| :--: | :--: |
|currency|格式化数字为货币格式。|
|filter|从数组项中选择一个子集。|
|lowercase|格式化字符串为小写。|
|orderBy|根据某个表达式排列数组。|
|uppercase|格式化字符串为大写。|

# 表达式中添加过滤器
过滤器可以通过一个管道字符 | 和一个过滤器添加到表达式中。
uppercase 过滤器将字符传格式化为大写:
``` html
<div ng-app="" ng-init="lastName='the last name!'">
    <p>姓名为 {{ lastName | uppercase }}</p>
</div>
```