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

## 表达式中添加过滤器

过滤器可以通过一个管道字符 | 和一个过滤器添加到表达式中。
uppercase 过滤器将字符传格式化为大写:

```html
<div ng-app="" ng-init="lastName='the last name!'">
    <p>姓名为 {{ lastName | uppercase }}</p>
</div>
```

lowercase 过滤器将字符串转化为小写:

```html
<div ng-app="myApp" ng-controller="personCtrl">
    <p>姓名:{{ lastName | lowercase }}</p>
</div>
```

## currency 过滤器

currency 过滤器将数字格式化为货币格式

```html
<div ng-app="myApp" ng-controller="cosCtrl">
    <input type="number" ng-model="quantity" />
    <input type="number" ng-model="proce" />
    <p>总价 = {{ (quantuty * price) | currency }}</p>
</div>
```

## 向指令添加过滤器

过滤器可以通过一个管道字符 (|) 和一个过滤器添加到指令中。
orderBy 过滤器根据表达式排列数组:

```html
<div ng-app="myApp" ng-controller="namesCtrl">
    <ul>
        <li ng-repeat="x in names | orderBy:'country'">
            {{ x.name + ', ' + x.country }}
        </li>
    </ul>
</div>
```
## 过滤输入
输入过滤器可以通过一个管道字符(|)和一个过滤器添加到指令中,该过滤器后跟一个冒号和一个模型名称。
filter 过滤器从数组中选择一个子集:
``` html
<div ng-app="myApp" ng-controller="namesCtrl">
    <p><input type="text" ng-model="test"></p>
    <ul>
        <li ng-repeat="x in names | filter:test | orderBy:'country'">
        {{ (x.name | uppercase) + ', ' + x.country }}
    </li>
</div>
```
# 自定义过滤器
以下实例是自定义一个过滤器 reverse,将字符串反转
``` html
<div ng-app="maApp" ng-controller="filterString">
    <div ng-controller="filterString">
        <div>{{wind | reverse}}</div>
    </div>
</div>
<script>
    var app = angular.module('myApp', []);
    app.controller("filterString", [
        "scope",
        function($scope) {
            $scope.wind = "七级大狂风"
        }
    ])
    app.filter('reverse', function(){
        return function(text) {
            return text.split("").reverse().join("");
        }
    })
</script>
```
> 文件 AngularJS过滤器.html