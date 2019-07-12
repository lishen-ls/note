# React
## 生命周期相关
### componentWillReceiveProps(nextProps)
- 初始化渲染时不触发，在每次接受到新的Props时触发，参数nextProps是新接受的Props，此时组件的this.props还未被改变成新的Props
- 同组件路由跳转通过判断Props中的match是否改变来决定是否AJAX
## Redux
### applyMiddleware
- Redux中间件
  ```javascript
  createStore(reducers,applyMiddleware(test));
  function example(){
    return function(dispatch){
      return function(action){
        dispatch(action);
      }
    }
  }
  ```
### redux-thunk
