# AngualrJS DOM

AngularJS 为 HTML DOM 元素的属性提供了绑定应用数据的指令

## ng-disabled 指令

ng-disabled 指令直接绑定应用程序数据到 HTML 的 disabled 属性。

```html
<div ng-app="" ng-init="mySwitch=true">
    <p><button ng-disabled="mySwitch">点我!</button></p>
    <p><input type="checkbox" ng-model="mySwitch" />按钮</p>
    <p>{{ mySwitch }}</p>
</div>
```

## ng-show

ng-show 指令隐藏或显示一个 HTML 元素。

```html
<div ng-app="">
    <p ng-show="true">我是可见的。</p>
    <p ng-show="false">我是不可见的。</p>
</div>
```

ng-show 指令根据 value 的值来显示(隐藏) HTML 元素。

```html
<div ng-app="" ng-init="hour=13">
    <p ng-show="hour > 12">我是可见的。</p>
</div>
```

## ng-hide

```html
<div ng-app="">
    <p ng-hide="true">我是不可见的。</p>
    <p ng-hide="false">我是可见的。</p>
</div>
```

**注:ng-if 的原理是移除和添加 DOM 结构,而 ng-show 和 ng-hide 则是设置*display:none*来显示或隐藏 DOM 结构**
