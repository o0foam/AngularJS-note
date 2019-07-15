# AngularJS 简介

AngularJS 是一种 JavaScript 框架。它通过指令扩展了 HTML,且通过表示大事绑定数据到 HTML。

# AngularJS 拓展了 HTML

AngularJS 通过 ng-directives 拓展了 HTML。
ng-app 指令定义一个 AngularJS 应用程序。
ng-model 指令把元素值(比如输入域的值)绑定到应用程序。
ng-bind 指令把应用程序数据绑定到 HTML 视图。**(也可以用 {{}} 表示)**

> 文件 AngularJS 简介-1.html

```html
<script src="./js/angular.js"></script>
<div ng-app="">
    <p>名字:<input type="text" ng-model="name" /></p>
    <h1>Hello {{name}}</h1>
</div>
```

实例讲解:

1. ng-app 指令告诉 AngularJS,\<div> 元素是 AngularJS 应用程序的"所有者"。
2. ng-model 指令把输入域的值绑定到应用程序变量 nmae。
3. ng-bind 指令把应用程序变量 name 绑定到某个段落的 innerHTML。 #什么

# 什么是 AngularJS?

AngularJS 使得开发现代的单一页面应用程序变得更加容易。

-   AngularJS 把应用程序数据绑定到 HTML 元素。
-   AngularJS 可以克隆和重复 HTML 元素。
-   AngularJS 可以影藏和现实 HTML 元素。
-   AngularJS 可以在 HTML 元素"背后"添加代码。
-   AngularJS 支持输入验证。

# AngularJS 指令

正如您锁看到的,AngularJS 指令是以 ng 作为前缀的 HTML 属性。
ng-init 指令初始化 AngularJS 应用程序变量。

> 文件 AngularJS 简介-2.html

```html
<script src="./js/angular.js"></script>
<div ng-app="" ng-init="firstName='John'">
    <p>姓名为<span>{{firstName}}</span></p>
</div>
```

# AngularJS 表达式

-   AngularJS 表达式写在双大括号内：{{ expression }}。
-   AngularJS 表达式把数据绑定到 HTML，这与 ng-bind 指令有异曲同工之妙。
-   AngularJS 将在表达式书写的位置"输出"数据。
-   AngularJS 表达式 很像 JavaScript 表达式：它们可以包含文字、运算符和变量。
    _实例 {{ 5 + 5 }}_

```html
<script src="./js/angular.js"></script>
<div ng-app="">
    <p>我的第一个表达式： {{ 5 + 5 }}</p>
</div>
```

# AngularJS 应用

AngularJS 模块 (Module) 定义了 AngularJS 应用。
AngularJS 控制器 (controller) 用于控制 Angular 应用。
ng-app 指令指明了应用, ng-controller 指明了控制器。

> 文件 AngularJS 简介-3.html

```html
<script src="./js/angular.js"></script>
<div ng-app="myApp" ng-controller="myController">
    姓名:<input type="text" ng-model="name" /><br />
    爱好:<input type="text" ng-model="Hobby" /><br />
    <span>{{name}}爱{{Hobby}}</span>
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.name = "少年";
            $scope.Hobby = "看球";
        }
    ]);
</script>
```

AngularJS 模块定义应用:

```JavaScript
var app = angular.module('myApp', []);
```

AngularJS 控制器:

```javascript
app.controller("myController", [
    "scope",
    function($scope) {
        $scope.name = "少年";
        $scope.Hobby = "看球";
    }
]);
```
