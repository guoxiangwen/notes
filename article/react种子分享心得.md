# React seed构建过程

## 写在前面

Facebook发布react之后，一直想找机会学一下,从官网到博客到问答，积累了点零散的知识,在github找了很多学习react的工程,不是项目太大就是配置太多,于是最近参考了vue-cli以及github上的一些开源项目,根据自己的喜好，包括目录结构,命名,文件存放,弄了一个react-starter

>地址:`https://github.com/guoxiangwen/react-starter`

## 目录结构

![react-starter](http://guoxw.qiniudn.com/react-starter.png)

## 集成的东西

>webpack2,react-router,less,nightwatch,jest,babel,没有集成redux因为不是所有项目都会用到它,如果你的项目要用，自行npm i就行了

## 开发环境

>开发环境下还是用的webpack-dev-server,并没有自己像vue-cli那样自己根据express来配置.这样已经够用了，而react官网的create-react-app是把所有配置都封装在了react-scripts中.对开发者来说不是很透明,也不知道发生了什么.`npm start`

## 生产环境

>生产环境大家可以自己跑一个静态server，例如:`http-server`,`anywhere`，用来访问build文件夹,项目的根目录中还准备了一个nginx.conf。用来配置nginx.大家只需要修改location的root就行了 `npm run build`

```nginx
        location / {
            root   G:\\workspace\\github\\react-starter\\build;
            index  index.html index.htm;
            try_files $uri $uri/ /index.html =404; #客户端开启html5mode
        }
```

## 测试

### unit测试

>这里用的是react官网推荐的jest `npm run unit`

### e2e测试

>虽然平时写e2e写得少，不过这里还是用到了nightwatch。`npm run e2e`

## 最后

>大家如果有什么建议可以到issue里面提.



