AngularJS 使用表达式把数据绑定到 HTML

# AngularJS 表达式

-   AngularJs 表达式写在双大括号内: {{ expression }。
-   AngularJs 表达式在数据绑定到 HTML,这与 ng-bind 指令有异曲同工之妙。
-   AngularJS 将表达式书写的位置"输出"数据。
-   AngularJS 表达式很像 Javascript 表达式: 它们可以包含文字、运算符和变量。

```html
<div ng-app="">
    <p>我的第一个表达式: {{ 5 + 5 }}</p>
</div>
```

# AngularJS 数字

AngularJS 数字就想 JavaScript 数字:

```html
<div ng-app="" ng-init="quantity=1;cost=5">
    <p>总价： {{ quantity * cost }}</p>
    <!-- 使用 ng-bind 的相同实例: -->
    <p>总价： <span ng-bind="quantity * cost"></span></p>
</div>
```

**使用 ng-init 不是很常见。您将在控制器一章中学习到一个更好的初始化数据的方式。**

# AngularJs 字符串

AngularJS 字符串就像 JavaScript 字符串:

```html
<div ng-app="" ng-init="firstName='John';lastName='Doe'">
    <p>姓名： {{ firstName + " " + lastName }}</p>
    <!-- 使用 ng-bind 的相同实例： -->
    <p>姓名： <span ng-bind="firstName + ' ' + lastName"></span></p>
</div>
```

# AngularJS 对象

AngularJS 对象就像 JavaScript 对象:

```html
<div ng-app="" ng-init="person={firstName:'John',lastName:'Doe'}">
    <p>姓为 {{ person.lastName }}</p>
    <!-- 使用 ng-bind 的相同实例： -->
    <p>姓为 <span ng-bind="person.lastName"></span></p>
</div>
```

# AngularJS 数组

```html
<div ng-app="" ng-init="points=[1,15,19,2,40]">
    <p>第三个值为 {{ points[2] }}</p>
    <!-- 使用 ng-bind 的相同实例： -->
    <p>第三个值为 <span ng-bind="points[2]"></span></p>
</div>
```

**以上实例全部可以看文件 _AngularJS 表达式.html_**

# AngularJs 表达式与 JavaScript 表达式

-   类似于 JavaScript 表达式，AngularJS 表达式可以包含字母，操作符，变量。
-   与 JavaScript 表达式不同，AngularJS 表达式可以写在 HTML 中。
-   与 JavaScript 表达式不同，AngularJS 表达式不支持条件判断，循环及异常。
-   与 JavaScript 表达式不同，AngularJS 表达式支持过滤器。
