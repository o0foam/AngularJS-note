AngularJS ng-model 指令用于绑定应用程序数据到 HTML 控制器(input,select,textarea)的值。

# ng-model 指令

ng-model 指令可以将输入域的值域 AngularJS 创建的变量绑定。

```html
<div ng-app="myApp" ng-controller="myController">
    名字:<input ng-model="name" />
</div>
<script>
    var app = angular.module("myApp", []);
    app.controller("myController", [
        "scope",
        function($scope) {
            $scope.name = "少年";
        }
    ]);
</script>
```

# 双向绑定

双向绑定,在修改输入域的值时,AngularJS 属性的值也会改变

# 验证用户输入

```html
<form name="myForm">
    Email:
    <input type="email" name="myEmail" ng-model="text" />
    <span ng-show="myForm.myEmail.$error.email">不是一个合法地址</span>
</form>
```

# 应用状态

ng-model 指令可以为应用数据提供状态值(invalid,dirty,touched,error):

```html
<form name="myForm2" ng-init="text2 = 'test@runoob.com'">
    Email:
    <input type="email" name="myEmail2" ng-model="text2" required></p>
    <h1>状态</h1>
    {{myForm2.myEmail2.$valid}}
    {{myForm2.myEmail2.$dirty}}
    {{myForm2.myEmail2.$touched}}
</form>
```

# CSS 类

```html
<style>
    input.ng-invalid {
        background-color: lightblue;
    }
</style>
<form name="myForm3">
    输入你的名字:
    <input name="myName" ng-model="text3" required />
    <p>文本域添加了 required 属性，该值是必须的，如果为空则是不合法的。</p>
</form>
```
ng-model 指令根据表单域的状态添加/移除以下类:
- ng-empty
- ng-not-empty
- ng-touched
- ng-untouched
- ng-valid
- ng-invaild
- ng-dirty
- ng-pending
- ng-pristine
> 文件 以上实例请看文件 AngularJs模型.html