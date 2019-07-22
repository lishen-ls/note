# React

## 生命周期相关

### componentWillReceiveProps(nextProps)

- 初始化渲染时不触发，在每次接受到新的 Props 时触发，参数 nextProps 是新接受的 Props，此时组件的 this.props 还未被改变成新的 Props
- 同组件路由跳转通过判断 Props 中的 match 是否改变来决定是否 AJAX

## Ref

> 不能在函数式组件上使用 ref，因为函数式组件没有实例，但是可以在函数式组件内部使用 ref，指向 class 组件和 DOM 元素

### React.createRef()

- 使用`React.createRef`创建，在元素或组件上使用`ref={xxx}`，引用名为 xxx，可用于获取高阶组件的子组件实例

  ```javascript
  import React, { Component } from "react";
  import ReactDOM, { render } from "react-dom";
  class Child extends Component {
    constructor() {
      super();
      this.myDiv = React.createRef();
    }
    componentDidMount() {
      console.log(this.myDiv.current);
    }
    render() {
      return <div ref={this.myDiv}>ref获取的dom元素</div>;
    }
  }
  ```

  ```javascript
  import React, { Component } from "react";
  import ReactDOM, { render } from "react-dom";
  class Child extends Component {
    constructor() {
      super();
    }
    componentDidMount() {}
    render() {
      return <div>子组件</div>;
    }
  }
  class Parent extends Component {
    constructor() {
      super();
      this.myChild = React.createRef();
    }
    componentDidMount() {
      console.log(this.myChild.current); //获取的是 Child 组件
    }
    render() {
      return <Child ref={this.myChild} />;
    }
  }
  ```

  ```javascript
  import React, { Component } from "react";
  import ReactDOM, { render } from "react-dom";
  class Child extends Component {
    constructor() {
      super();
    }
    componentDidMount() {}
    render() {
      return <div ref={this.props.myRef}>子组件</div>;
    }
  }
  class Parent extends Component {
    constructor() {
      super();
      this.myChild = React.createRef();
    }
    componentDidMount() {
      console.log(this.myChild.current); //获取的是 Child 组件中的DOM元素
    }
    render() {
      return <Child myRef={this.myChild} />;
    }
  }
  ```

### 函数中获取元素

```javascript
 //在元素的ref属性上使用函数，其参数为该元素
  ref={
    ref=>{
      //...
    }
  }
//or
  ref={
    this.func
  }
```

> 函数式组件可以使用`useRef`来访问获取元素,`useRef.current`可以存储任何值，并且可变，例如`useRef(1)`，其返回值为`{current:1}`

### React.forwartRef()

## Redux

### 流程

- UI -> Actions -> Reducers -> Store -> UI

### applyMiddleware

- Redux 中间件

```javascript
createStore(reducers, applyMiddleware(test));
function example() {
  return function(dispatch) {
    return function(action) {
      dispatch(action);
    };
  };
}
```

### redux-thunk

### redux-saga

-

## Hook
