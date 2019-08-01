# AngularJs selct（选择框）

AngularJS 可以使用数组或对象创建一个下拉列表选项。

## 使用 ng-options 创建选择框

在 AngularJs 中我们可以使用 ng-option 指令来创建一个下拉列表,列表通过对象和数组循环输出,如下示例:

```html
<div ng-app="myApp" ng-controller="myCtrl">
    <h1>ng-option</h1>
    <select
        ng-model="selecteName"
        ng-options="item.value as item.name for item in options"
    >
    </select>
    <h1>ng-repeat</h1>
    <select ng-model="selecteName">
        <option value="{{item.value}}" ng-repeat="item in options"
            >{{item.name}}</option
        >
    </select>
    <h1>两者区别:</h1>
    <!-- <select ng-model="res1" ng-options="item.value as item.name for item in animals">
            </select> -->
    <select ng-model="res1" ng-options="item.name for item in animals">
    </select>
    <p>res1.name:{{res1.name}}</p>
    <p>res1.hobby:{{res1.hobby}}</p>
    <p>res1:{{res1}}</p>
    <select ng-model="res2">
        <option value="{{item.hobby}}" ng-repeat="item in animals"
            >{{item.name}}</option
        >
    </select>
    <p>res2.name:{{res2.name}}</p>
    <p>res2.hobby:{{res2.hobby}}</p>
    <p>res2:{{res2}}</p>
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myCtrl", [
        "scope",
        function($scope) {
            $scope.options = [
                { name: "第一项", value: "1" },
                { name: "第二项", value: "2" },
                { name: "第三项", value: "3" }
            ];
            $scope.selecteName = "2";
            $scope.res1 = "";
            $scope.res2 = "";
            $scope.animals = [
                { name: "duck", hobby: "swim" },
                { name: "bird", hobby: "fly" },
                { name: "chicken", hobby: "crow" }
            ];
        }
    ]);
</script>
```

> 文件 AngularJS Select.html
