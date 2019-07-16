-   AngularJS 通过被称为指令的新属性来拓展 HTML。
-   AngularJS 通过内置的指令来为应用添加功能。
-   AngularJS 允许你自定义指令。

# AngularJS 指令

-   AngularJS 指令是拓展的 HTML 属性,带有前缀 ng-。
-   ng-app 指令初始化一个 AngularJS 应用程序。
-   ng-init 指令初始化应用程序数据。
-   ng-model 指令把元素值(比如输入域的值)绑定到应用程序。

```html
<div ng-app="" ng-init="firstName='John'">
    <p>在输入框中尝试输入：</p>
    <p>姓名：<input type="text" ng-model="firstName" /></p>
    <p>你输入的为： {{ firstName }}</p>
</div>
```

ng-app 告诉 AngularJs,\<div> 元素是 AngularJS 数据绑定表达式。

# 数据绑定

上面实例中 {{ firstName }} 表达式是一个 AngularJS 数据绑定表达式。AngularJS 中数据绑定,同步了 AngularJS 表达式与 AngularJS 数据。\*\*{{firstName}} 是通过 ng-model="firstName" 进行同步。
在写一个实例中,两个文本域是通过两个 ng-model 指令同步的:

```html
<div ng-app="" ng-init="quantity=1;price=5">
    <h2>价格计算器</h2>
    数量： <input type="number" ng-model="quantity" /> 价格：
    <input type="number" ng-model="price" />
    <p><b>总价：</b> {{ quantity * price }}</p>
</div>
```

**一般不推荐使用 ng-init**

# 重复 HTML 元素

ng-repeat 指令会重复一个 HTML 元素:

```html
<div ng-app="" ng-init="names=['Jani','Hege','Kai']">
    <p>使用 ng-repeat 来循环数组</p>
    <ul>
        <li ng-repeat="item in names">
            {{ item }}
        </li>
    </ul>
</div>
```

ng-repeat 指令用在一个对象数组上:

```html
<div ng-init="names=['Janni', 'Hege', 'Kai']">
    <p>使用 ng-repeat来循环数组</p>
    <ul>
        <li ng-repeat="item in names">
            {{ item }}
        </li>
    </ul>
</div>
<div
    ng-init="person=[
        {name:'Jani',country:'Norway'},
        {name:'Hege',country:'Sweden'},
        {name:'Kai',country:'Denmark'}]"
>
    <p>循环对象</p>
    <ul>
        <li ng-repeat="item in person">
            {{ item.name + ' come from ' + item.country}}
        </li>
    </ul>
</div>
```

**AngularJS 完美支持数据库的 CRUD (增删改查)应用程序。把实例中的对象想象成数据库中的记录。**

# ng-app 指令

-   ng-app 指令定义了 AngularJS 应用程序的根元素。
-   ng-app 指令在网页加载完毕时自动引导(自动初始化)应用程序。

# ng-init 指令

-   ng-init 指令为 AngularJS 应用程序定义了初始值。
-   **通常情况下,不使用 ng-init,您将使用一个控制器或模块来代替它。**

# ng-model 指令

ng-model 指令绑定 HTML 元素到应用程序数据。
ng-model 指令也可以:

-   为应用程序数据提供类型验证(number、email、required)。
-   为应用程序数据提供状态(invaild、dirty、touched、error)。
-   为 HTML 元素提供 CSS 类。
-   绑定 HTML 元素到 HTML 表单。

# ng-repeat 指令

ng-repeat 指令对于集合中(数组中)的每个项会克隆一次 HTML 元素。

# 创建自定义的指令

除了 AngularJS 内置的指令外,我们还可以创建自定义指令。你可以使用 **.directive** 函数来添加自定义的指令。要调用自定义指令, HTML 元素上需要添加自定义指令名。使用驼峰发来命名一个指令,但在使用它时需要以-分割,比如: runoobDirective => runoob-directive:

```HTML
<div ng-app="myApp">
    <runoob-directive></runoob-directive>
</div>
<script>
    var app = angular.module("myApp", []);
    app.directive("runoobDirective", function(){
        return {
            template: "<h1>自定义指令!</h1>"
        }
    })
</script>
```

你可以通过以下方式来调用指令:

## 元素名:

```html
<runoob-directive></runoob-directive>
```

## 属性:

```html
<div runoob-directive></div>
```

## 类名:

```html
<div ng-app="myApp">
    <div class="runoob-directive"></div>
    <p><b>注意： 你必须设置 restrict 的值为 "C" 才能通过类名来调用指令。</b></p>
</div>
<script>
    var app = angular.module("myApp", []);
    app.directive("runoobDirective", function() {
        return {
            restrict: "C",
            template: "<h1>自定义指令!</h1>"
        };
    });
</script>
```

## 注释

```html
<div ng-app="myApp">
    <!-- directive: runoob-directive -->
    <p><b>注意： 你必须设置 restrict 的值为 "M" 才能通过注释来调用指令。</b></p>
    <p>
        <b>注意： 我们需要在该实例添加 replace 属性， 否则评论是不可见的。</b>
    </p>
</div>
<script>
    var app = angular.module("myApp", []);
    app.directive("runoobDirective", function() {
        return {
            restrict: "M",
            replace: true,
            template: "<h1>自定义指令!</h1>"
        };
    });
</script>
```

# 限制使用

你可以限制你的指令只能通过特定的方式来调用,**restrict** 的值可以是下面几种:

-   E:作为元素名使用;
-   A:作为属性使用;
-   C:作为类名使用;
-   M:作为注释使用。
    **restrict 的默认值是 EA,既可以通过元素名和属性名来调用指令。**

> 文件 以上实例请看文件 AngularJS 指令.html
