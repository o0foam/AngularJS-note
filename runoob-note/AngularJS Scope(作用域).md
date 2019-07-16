Scope(作用域)是应用在 HTML(视图)和 JavaScript(控制器之间的纽带)。Scope 是一个对象,有可用的方法和属性。Scope 可应用在视图和控制器上。

# 如何使用 Scope

当你在 AngularJs 创建控制器时,你可以将 \$scope 对象当做一个参数传递:

```html
<div ng-app="myApp" ng-controller="myController">
    <h1>{{ carName }}</h1>
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.carName = "happy";
        }
    ]);
</script>
```

当在控制器中添加 \$scope 对象时,视图 (HTML) 获取了这些属性。

# Scope 概述

AngularJS 应用组成如下:

-   View(视图),即 HTML。
-   Model(模型),当前视图中可用的数据。
-   Controller(控制器),即 JavaScript 函数,可以添加或修改属性。
    scope 是模型,是一个 JavaScript 对象,带有属性和方法,这些属性和方法可以在视图和控制器中使用。

```html
<div ng-app="myApp" ng-controller="myController">
    <input type="text" ng-model="name" />
    <h1>{{changeText}}</h1>
    <button ng-click="sayHello()">点我</button>
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.name = "";
            $scope.sayHello = function() {
                $scope.changeText = "Hello " + $scope.name + "!";
            };
        }
    ]);
</script>
```

# Scope 作用范围

了解你当前使用的 scope 是非常重要的,以上两个实例中,只有一个作用域 scope,所以处理起来比较简单,但在大型项目中,HTML DOM 中有多个作用域,这是你就需要知道你使用的 scope 对应的作用域是哪一个了。

```html
<ul>
    <li ng-repeat="item in animal">{{item}}</li>
</ul>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.animal = ["fish", "duck", "bird"];
        }
    ]);
</script>
```

> 文件 以上实例请看文件 AngularJS Scope(作用域)-1.html

# 根作用域

所有应用都有一个 $rootScope,它可以作用在 ng-app 指令包含的所有 HTML 元素中。
$rootScope 可作用于整个应用中。是各个 controller 中 scope 的桥梁。用 rootscope 定义的值,可以在各个 controller 中使用。

```html
<div ng-app="myApp" ng-controller="myController">
    <h1>家族成员:{{lastName}}</h1>
    <ul>
        <li ng-repeat="item in animals">
            {{lastName + item}}
        </li>
    </ul>
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.animals = ["duck", "fish", "bird"];
        }
    ]);
    // run方法用于初始化全局的数据，仅对全局作用域起作用。这里的run方法只会在angular启动的时候运行一次。
    app.run(function($rootScope) {
        console.log($rootScope);
        $rootScope.lastName = "可达鸭在看";
    });
</script>
```

> 文件 AngularJS Scope(作用域)-2.html
