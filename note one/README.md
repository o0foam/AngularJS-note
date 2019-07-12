学习资料源自: [AngularJS 慕课手记](https://www.imooc.com/article/260273)
# 介绍

AngularJS 最初由 Misko Hevery 和 Adam Abrons 于 2009 年开发,后来成为了 Google 公司的项目。AngularJS 弥补了 HTML 在构建应用方面的不足,其通过使用标识符(directives)勾结,来扩展 Web 应用中的 HTML 词汇,使开发者可以使用 HTML 来声明动态内容,从而使得 Web 开发和测试变得更加容易。
AngularJS 版本简介
[AngularJS 网址](https://github.com/angular/angular.js/releases/)

# AngularJS 功能:

AngularJS 是专门为应用程序设计的 HTML。
AngularJS 使得开发现代的打你页面应用程序(SPA)变得更加容易

1. AngularJS 把应用程序数据绑定到 HTML 元素。
2. AngularJS 可以克隆和复制重复的 HTML 元素。
3. AngularJS 可以影藏和现实 HTML 元素。
4. AngularJS 可以在 HTML 元素"背后"添加代码。
5. AngularJS 支持输入验证。

# AngularJS 主要特性:

1. MVC
2. 模块化与依赖注入
3. 双向数据绑定
4. 指令与 UI 空间

# AngularJS 资源:

[AngularJS 官方网站](http://AngularJS.org)
[AngularJS Api](http://docs.AngularJS.cn/api)
[AngularJS 中文网](http://www.AngularJS.cn/)
[AngularJS 社区](http://www.ngnice.com/)
[AngularJS gitHub](https://github.com/angular)
[AngularJS 下载](http://www.bootcdn.cn/angular.js/)
通过 nodejs 下载:

> npm install angular

# AngularJS 的使用:

1. 下载加载 angular.js 库
2. 使用 **ng-app** 指令告诉 angular 应该管理 DOM 中的哪一部分
   > 文件 helloWorld.hmtl

```html
<div ng-app="">
  <p>在输入框中尝试输入：</p>
  <p>姓名： <input type="text" ng-model="name" /></p>
  <p ng-bind="name"></p>
</div>
```

# AngularJS 中常用名词,也就是所说的常用指令

- HTML5 允许拓展的(自制的)属性,以 data- 开头。
- AngularJS 属性以 ng- 开头,但是您可以使用 data-ng- 来让网页对 HMTL5 有效
  俗话说:下面的指令可以在开头加上 data- 例如 ng-app 等同于 data-ng-app

| 指令          |                   描述                   |      讲解 |
| ------------- | :--------------------------------------: | --------: |
| ng-app        |           定义应用程序的根元素           |      指令 |
| ng-bind       |       绑定 HTML 元素到应用程序数据       |      简介 |
| ng-click      |          定义元素被单击时的行为          | HTML 事件 |
| ng-controller |         为应用程序定义控制器对象         |    控制器 |
| ng-disabled   | 绑定应用程序数据到 HTML 的 disabled 属性 |  HTML DOM |
| ng-init       |           为应用程序定义初始值           |      指令 |
| ng-model      |       绑定应用程序数据到 HTML 元素       |      指令 |
| ng-repeat     |     为控制器中的每个数据定义一个模板     |      指令 |
| ng-show       |           显示或隐藏 HTML 元素           |  HTML DOM |

## ng-app、ng-bind、ng-model 和 {{}} 案例演示

### ng-app:

ng-app 指令定义了 AngularJS 应用程序的根元素。
ng-app 指令在网页在家完毕时会自动引导(自动初始化)应用程序。稍后您将学习到 ng-app 如何通过一个值(比如 ng-app="myModule") 连接到代码模块。

### ng-model 指令:

ng-model 指令绑定 HTML 元素到应用程序数据。
ng-model 指令也可以:

- 为应用程序数据提供类型验证 (number、email、required)。
- 为应用程序数据提供状态 (invalid、dirty、touched、error)。
- 为 HTML 元素到 HTML 表单。
- ng-bind 指令等同于 {{}}
- 绑定 HTML 元素到应用程序数据

**_示例_**
{{}} 等同于 ng-bind

> 文件 ng-model.html

```html
<div ng-app="">
  <p>在输入框中尝试输入：</p>
  <p>姓名： <input type="text" ng-model="name" /></p>
  <p>{{ name }}</p>
  <p ng-bind="name"></p>
</div>
```

实例讲解：
当网页加载完毕， AngularJS 自动开启。

- **ng-app** 指令告诉 AngularJS, \<div> 元素是 AngularJS 应用程序的"所有者"。
- **ng-model** 指令把输入域的值绑定到应用程序变量 name。
- **ng-bind** 指令吧应用程序变量 name 绑定到某个段落的 innerHTML

### ng-init 指令

**ng-init** 指令为 AngularJS 应用程序定义了初始值。
通常情况下,不使用 ng-init。你讲使用一个控制器或模块来代替它。
**_示例_**

> 文件 ng-init.html

```html
<div ng-app="" ng-init="firstName='John'">
  <p>姓名为 <span ng-bind="firstName"></span></p>
</div>
```

### AngularJS 表达式

- AngularJS 表达式写在双大括号内: 'exoression'。
- AngularJS 表达式把数据绑定到 HTML,这与 ng-bind 指令有异曲同工之妙。
- AngularJS 将在表达式书写的位置"输出"数据。
- AngularJS 表达式很像 JavaScript 表达式: 它们可以包含文字、运算符和变量。
  **_示例_**
  > 文件 AngularJS-表达式.html

### AngularJS 控制器

- AngularJS 控制器控制 AngularJS 应用程序的数据;
- AngularJS 控制器是常规的 JavaScript 对象;
- AngularJS 应用程序被控制器控制;
- ng-controller 指令定义了应用程序控制器;
- 控制器是 JavaScript 对象,由标准的 JavaScript 对象的构造函数创建;
- 控制器的 \scope 是控制器锁指向的应用程序 HTML 元素;
- AngularJS 中 \scope 是链接 controllers(控制器) 和 templates(模板 view/视图) 的主要胶合体;
  我们可以把我们的 model 存放在 scope 上,来达到双向绑定。
  **_示例 1_**
  > 文件 AngularJS-控制器.html

```html
<!DOCTYPE html>
<html>
  <body>
    <script src="./angular.js"></script>
    <div ng-app="app">
      <div ng-controller="personController">
        名: <input type="text" ng-model="person.firstName" /><br />
        姓: <input type="text" ng-model="person.lastName" /><br />
        <p>姓名: {{ person.firstName + " " + person.lastName }}</p>
        <span>姓名: {{ name }}</span>
      </div>
    </div>
    <script>
      // 写法 1:
      var app = angular.module("app", []);
      app.controller("personController", [
        "scope",
        function(scope) {
          scope.person = {
            firstName: "John",
            lastName: "Doe"
          };
          // 因为只会进行执行一次,不会一直监听,所以这里只触发一次,所以之后改变 firstName 和 lastName 时,name的值并不会改变
          scope.name = scope.person.firstName + " " + scope.person.lastName;
        }
      ]);

      // 写法 2:
      // var app = angular.module("app",[]);
      // var init = function(scope){
      //     scope.person = {
      //         firstName: "John",
      //         lastName: "Doe"
      //     };
      //     scope.name = scope.person.firstName + " " + scope.person.lastName;
      //     console.log(scope.name)
      // }
      // app.controller("personController", init);
    </script>
  </body>
</html>
```

实例讲解:

- AngularJS 应用程序由 ng-app 定义。应用程序在 \<div> 内运行。
- ng-controller 指令把控制器命名为 personController 。
- 控制对象有一个属性: scope.person。
- ng-model 指令绑定输入域到控制器的属性 ( firstName 和 lastName)。
  **_示例 2_**
  > 文件 AngularJS-ng-repeat.html

```html
<!DOCTYPE html>
<html lang="en">
  <body>
    <div ng-app="app" ng-controller="repeatController">
      <li>
        <li ng-repeat="item in arr">
          {{ item.name + ", " + item.country }}
        </li>
      </li>
    </div>
    <script src="./angular.js"></script>
    <script>
      var app = angular.module("app", []);
      function init(scope) {
        scope.arr = [
          { name: "Jani", country: "Norway" },
          { name: "Hege", country: "Sweden" },
          { name: "Kai", country: "Denmark" }
        ];
      }
      app.controller("repeatController", init);
    </script>
  </body>
</html>
```
