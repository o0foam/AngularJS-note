# AngularJS 事件

AngularJS 有自己的 HTML 事件指令。

## ng-click 指令定义了 AngularJS 点击事件

```html
<div ng-app="" ng-controller="myCtrl">
    <button ng-click="count = count + 1">点我！</button>
    <p>{{ count }}</p>
</div>
```
