# scss

```
sass --watch test.scss:test.css --style compact
```

## 定义变量
```scss
$baseLineHeight: 1.5;
$baseLineHeight: 1.5 !default;
```

## sass嵌套
```scss
nav {
  a {
    header & {
      color:green;
    }
  }  
}
```

## 属性嵌套(有相同的属性前缀)
```scss
// .box { font-size: 12px; font-weight: bold; }
.box {
  font: {
   size: 12px;
   weight: bold;
  }  
}
```

## 伪类嵌套
```scss
.clearfix {
    &:before,
    &:after {
        content: "";
        display: table;
    }
    &:after {
        clear: both;
        overflow: hidden;
    }
}
```


## 声明混合宏

```scss
@mixin border-radius {
    -webkit-border-radius: 5px;
    border-radius: 5px;
}

button {
    @include border-radius;
}
```

## 混合宏的参数

```scss
@mixin border-radius($radius: 3px){
  -webkit-border-radius: $radius;
  border-radius: $radius;
}
.box {
  @include border-radius(3px);
}
```

## sass 继承
```scss
.btn {
  border: 1px solid #ccc;
  padding: 6px 10px;
  font-size: 14px;
}
.btn-primary {
  background-color: #f36;
  color: #fff;
  @extend .btn;
}
```