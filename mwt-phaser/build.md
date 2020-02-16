### 项目介绍

#### 项目启动
* npm start --dir=A
    * 参数说明A：是指 src/views目录下面的文件夹，是项目的入口，它可以是editor，mwt，picture，web（views下面的文件名）
    * 当A=editor时需要先使用，npm run login，否则会缺失cookie，导致编译失败，登录时输入伴鱼账号，不需要密码
* 当项目启动后在域名 + 端口后补全项目目录，ex: 
    * npm start --dir=eidtor 
    * 在浏览器键入地址https://localhost:30001/editor/index.html#/create?type=mwt&cid=318947195936822&bookid=211648353613834&title=Aa
    * 参数可以在[绘本管理后台](https://test.ipalfish.com:30000/picture-book/picturebookmanage/index)打开any一个绘本得到参数进行本地调试。

### 项目结构介绍
```
palfish_rtc
│   README.md
│   package.json // 依赖包
│    <---配置文件--->
│   postcss.verify.js
│   prettier.verify.js
│   sentry.verify.js
│   .eslintrc.js
│   .babelrc
│     <---配置文件--->
│
└───src
│
│   └───views  // 打包js入口目录(引入container)
│
│       └───picture // 绘本课堂
│       └───editor  // 课件编辑入口目录
│       └───web  // web pc 端入口
│       └───mwt  // 点读
│
│   └─── containers  // 容器目录，存放根组件
│
│   └─── components  // 组件目录，存放通用组件
│
│   └─── images  // 图片目录
│
│         │ logo.png //通用图片
│         └───client  // 各业务图片
│                  │ xx1.png
│                  │ xx2.png
│
│   └─── less  // 样式目录
│
│   └─── utils  // 工具目录
│
│   └─── sync  // 同步逻辑
│
│        └─── client //客户端同步逻辑
│
│        └─── serve //服务端同步逻辑
│
│        └─── script // 同步脚本 包括webpack配置


```