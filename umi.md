# umi

## 配置代理

- .umirc.js
  ```javascript
  devServer:{
    proxy:{
      '/api':{
        target:'http://localhost:4000',
        pathRewrite:{'^/api':''},
        changeOrigin:true
      }
    }
  }
  ```
