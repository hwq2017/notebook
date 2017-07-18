
## React
react 示例代码:
```c
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta http-equiv="X-UA-Compatible" content="ie=edge">
  <script src="https://cdn.bootcss.com/react/15.6.1/react.js"></script>
  <script src="https://cdn.bootcss.com/react/15.6.1/react-dom.js"></script>
  <script src="https://cdn.bootcss.com/babel-core/5.8.38/browser.js"></script>
  <title>Document</title>
</head>
<body>
// 真DOM
  <div id="d1"></div>
  <script type="text/babel">

// 虚拟的DOM
    ReactDOM.render(     // 将模板转为html语言,插入指定的DOM中
     <h1>hello world<h1/>,// 模板
      document.getElementById('d1')
    );
  </script>
</body>
</html>
```
1. 上述代码中<script> 的 type属性为 "text/babel",**babel**为JSX语法解释器,用来解析React独有的JSX语法,允许html和js的混合写法
2. 前面的引用了三个库文件. react.js, 是react是核心库文件. react-dom.js, 是提供与DOM相关的功能, Browser.js的作用是将JSX语法转为Javascript语法.

#### react语法

1. 在react中,组件就相当于html中的标签,在创建组件时,首字母必须大写,React允许将代码封装成组件, 然后你插入普通HTML标签一样, 在网页中插入这个组件

2. 写js代码时,必须写在花括号内,下面的基本语法规则是遇到HTML标签以<开头>结束的. 就用HTML规则解析. 遇到代码块以{开头}结束就使用JS规则进行解析.

3. 添加组件属性,this.props对象属性与组件的主席一一对应,this.props.children例外,需要注意就是class属性需要写成className, for属性需要写成htmlFor, 因为class和for是JavaScript的保留字.
可以把 props 看成组件的配置属性，在组件内部是不变的，只是在调用这个组件的时候传入不同的属性来定制显示这个组件。**见例3**

4. #### React.creatClass()方法

用于生成一个组件类,且都必须有自己的**render**方法,用于输出组件, 组件类在render的return中只能只能包含一个顶层标签,顶层标签
里可以嵌套多个标签


例:
1.
```c
<script type="text/babel">
    var names = ['lisi','zhangsan','wangwu'];
    
    // 创建组件
    var CommentBox = React.createClass({
      render:function(){
        return (
          <div>
          { // react 语法中,js 代码 必须写在 {} 里
          names.map(function(name){
            return <h1 key={name.toString()}>hello  {name}!!!!!!!!!!</h1>
          })
        }

        </div>
      )
    }
  })
  ReactDOM.render(
    <CommentBox />,
    document.getElementById('d1')
  );
  </script>
```
2.
```c
<script type="text/babel">
    // 组件首字母必须大写,
    var CommentBox = React.createClass({
      render:function(){
        return (
             <div>
             <h1> myname is {this.props.name}</h1>
             <h1>age : {this.props.age} {this.props.className}</h1>
             </div>

        )
      }
    })
    ReactDOM.render(
      <CommentBox name="lisi" age="18" className="haha"/>,
      document.getElementById('d')
    )
  </script>
```

