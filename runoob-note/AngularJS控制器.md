AngularJS 控制器控制 AngularJS 应用程序的数据。AngularJS 控制器是常规的 JavaScript 对象。

# AngularJS 控制器

-   AngularJS 应用程序被控制器控制。
-   ng-controller 指令定义了应用程序控制器局号
    控制器是 JavaScript 对象,由标准的 JavaScript 对象的构造函数创建。

```html
<div ng-app="myApp" ng-controller="myController">
    名:<input type="text" ng-model="firstName" /><br />
    姓:<input type="text" ng-model="lastName" /><br />
    姓名: {{firstName + " " + lastName}}
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.firstName = "John";
            $scope.lastName = "Doe";
        }
    ]);
</script>
```

应用解析：

1. AngularJS 应用程序由 ng-app 定义。应用程序在 <div> 内运行。
2. ng-controller="myController" 属性是一个 AngularJS 指令。用于定义一个控制器。
3. myController 函数是一个 JavaScript 函数。
4. AngularJS 使用\$scope 对象来调用控制器。
5. 在 AngularJS 中， \$scope 是一个应用对象(属于应用变量和函数)。
6. 控制器的 \$scope （相当于作用域、控制范围）用来保存 AngularJS Model(模型)的对象。
7. 控制器在作用域中创建了两个属性 (firstName 和 lastName)。
8. ng-model 指令绑定输入域到控制器的属性（firstName 和 lastName）。

# 控制器方法

上面的实例演示了一个带有 lastName 和 firstName 这两个属性的控制对象。
控制器也可以有方法(变量和函数):

```html
<div ng-app="myApp" ng-controller="myController">
    名:<input type="text" ng-model="firstName" /><br />
    姓:<input type="text" ng-model="lastName" /><br />
    姓名: {{fullName}}
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.firstName = "John";
            $scope.lastName = "Doe";

            // 控制器方法
            $scope.fullName = function() {
                return $scope.firstName + " " + $scope.lastName;
            };
        }
    ]);
</script>
```
