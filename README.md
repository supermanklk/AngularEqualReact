
### 参考手册
https://www.runoob.com/angularjs/angularjs-reference.html


### for

``` 
<div data-ng-app="" data-ng-init="names=['Jani','Hege','Kai']">
  <p>使用 ng-repeat 来循环数组</p>
  <ul>
    <li data-ng-repeat="x in names">
      {{ x }}
    </li>
  </ul>
</div>
```

```
<div ng-app="myApp" ng-controller="myCtrl">

<ul>
    <li ng-repeat="x in names">{{x}}</li>
</ul>

</div>

<script>
var app = angular.module('myApp', []);

app.controller('myCtrl', function($scope) {
    $scope.names = ["Emil", "Tobias", "Linus"];
});
</script>
```


### ng-app ng-controller angular.module

```
<div ng-app="myApp" ng-controller="myCtrl">
名字: <input ng-model="name">
</div>

<script>
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope) {
    $scope.name = "John Doe";
});
</script>

```

### 双向绑定

### 作用域
Scope(作用域) 是应用在 HTML (视图) 和 JavaScript (控制器)之间的纽带。
Scope 是一个对象，有可用的方法和属性。


```
<div ng-app="myApp" ng-controller="myCtrl">

<h1>{{carname}}</h1>

</div>

<script>
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope) {
    $scope.carname = "Volvo";
});
</script>
```

```
<button ng-click='sayHello()'>点我</button>	
```



### AngularJS 服务(Service)
```
var app = angular.module('myApp', []);
app.controller('customersCtrl', function($scope, $location) {
    $scope.myUrl = $location.absUrl();
});
```

### 发送请求
```
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope, $http) {
  $http.get("welcome.htm").then(function (response) {
      $scope.myWelcome = response.data;
  });
});
```

### timeout interval
```
var app = angular.module('myApp', []);
app.controller('myCtrl', function($scope, $timeout) {
  $scope.myHeader = "Hello World!";
  $timeout(function () {
      $scope.myHeader = "How are you today?";
  }, 2000);
});
```



```
ng-disabled
ng-show
ng-hide
```



### directive

```
<div ng-app="myApp" runoob-directive></div>

<script>

var app = angular.module("myApp", []);

app.directive("runoobDirective", function() {
    return {
        template : "我在指令构造器中创建!"
    };
});
```


### 包含

```
<div ng-include="'runoob.htm'"></div>



认情况下， ng-include 指令不允许包含其他域名的文件。如果你需要包含其他域名的文件，你需要设置域名访问白名单
app.config(function($sceDelegateProvider) {
    $sceDelegateProvider.resourceUrlWhitelist([
        'https://c.runoob.com/runoobtest/**'
    ]);
});
<div ng-include="'https://c.runoob.com/runoobtest/angular_include.php'"></div>
```


### 依赖注入


### 路由
```
https://www.runoob.com/angularjs/angularjs-routing.html
```
