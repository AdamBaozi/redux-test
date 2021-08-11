# redux-test
一、项目来源于：https://segmentfault.com/a/1190000004355491?_ea=661485
在将项目在本地实现的过程中，出现了一些问题，于是在原项目的基础上相应地做了改动。
1.bebel-loader版本不匹配的问题
详细是TypeError: Cannot read property 'babel' of undefined
解决办法参考：TypeError: Cannot read property 'babel' of undefined
2.
babel-loader jsx SyntaxError: Unexpected token [duplicate]
解决办法参考：https://stackoverflow.com/questions/33460420/babel-loader-jsx-syntaxerror-unexpected-token

这样之后，通过键入命令： webpack  => 成功将项目打包至bundle.js

二、将项目部署到服务器
参考：https://segmentfault.com/a/1190000006670084
主要步骤是：
1.修改package.json文件，添加如下：
"scripts": {
    "dev": "webpack-dev-server --devtool eval-source-map --progress --colors --hot --inline --content-base ./",
    "build": "webpack --progress --colors"
  },
  
--content-base path: 需要特别注意，path主要是指index.html相对于根目录的位置，在本项目中，index.html处于一个路径下，所以path描述为./即可
 2.输入npm run dev
 3.在浏览器中打开localhost:8080/index.html
