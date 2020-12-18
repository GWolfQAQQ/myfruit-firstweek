<template>
  <div class="home">
     物联网项目注释

     vue.config.js
      #导入path模块
      const path = require("path");
      #将路径片段使用特定的分隔符（window：\）连接起来形成路径
      function resolve(dir) {
        return path.join(__dirname, dir);
      }
      module.exports = {
        #保存时是否使用eslint
        lintOnSave: false,

        # 部署应用包时的基本 URL
        publicPath: "/cyberway-iot/admin/dev",

        #alias设置别名
        chainWebpack: config => {
          config.resolve.alias.set("cyberway-iot-devicemanagement", __dirname);
        }
      };

      postcss.config.js
      #自动添加浏览器内核前缀
      autoprefixer: {}

      Dockerfile
      #指定nginx镜像
      FROM nginx
      #将打包后的dist文件复制到linux上的/usr/share/nginx/html
      COPY dist /usr/share/nginx/html

      .eslintrc.js

      "off"或者0    //关闭规则关闭
      "warn"或者1    //在打开的规则作为警告（不影响退出代码）
      "error"或者2    //把规则作为一个错误（退出代码触发时为1）

      module.exports = {
        #告诉eslint找当前配置文件不能往父级查找
        root: true,
        #指定环境的全局变量，下面的配置指定为node环境
        env: {
          node: true
        },
        #指定代码遵循什么规范
        extends: ["plugin:vue/essential", "@vue/prettier"],

        #no-console//禁止使用console
        #no-debugger//禁止使用debugger
        rules: {
          "no-console": process.env.NODE_ENV === "production" ? "error" : "off",
          "no-debugger": process.env.NODE_ENV === "production" ? "error" : "off"
        },
        #指定解析器
        parserOptions: {
          parser: "babel-eslint"
        }
      };

      .browserslistrc
      浏览器兼容
      > 1%:代表着全球超过1%人使用的浏览器
      last 2 versions: 表示所有浏览器兼容到最后两个版本
      :表示IE浏览器版本大于8（实则用npx browserslist 跑出来不包含IE9 ）

      webpack.config.js配置项的意义和作用

      outputDir: 将构建好的文件输出到哪里（或者说将编译的文件）
      assetsDir:放置生成的静态资源 (js、css、img、fonts) 的目录
      indexPath:指定生成的 index.html 的输出路径 (相对于 outputDir)。也可以是一个绝对路径
      publicPath:部署应用包时的基本 URL
      filenameHashing:默认情况下，生成的静态资源在它们的文件名中包含了 hash 以便更好的控制缓存。
      然而，这也要求 index 的 HTML 是被 Vue CLI 自动生成的
      pages:在 multi-page（多页）模式下构建应用。每个“page”应该有一个对应的 JavaScript 入口文件
      lintOnSave:是否在保存的时候使用 `eslint-loader` 进行检查
      runtimeCompiler:是否使用包含运行时编译器的 Vue 构建版本
      transpileDependencies:默认情况下 babel-loader 会忽略所有 node_modules 中的文件
      Webpack相关配置
      configureWebpack:
      如果这个值是一个对象，则会通过 webpack-merge 合并到最终的配置中。
      如果这个值是一个函数，则会接收被解析的配置作为参数。
      chainWebpack:是一个函数，会接收一个基于 webpack-chain 的 ChainableConfig 实例。
      允许对内部的 webpack 配置进行更细粒度的修改
      配置 webpack-dev-server 行为
      可设置代理proxy
      自动打开浏览器
      open: false,
      CSS 相关选项
      css.modules
      runtimeCompiler:使用带有浏览器内编译器的完整构建版本
      loaderOptions: 为预处理器的 loader 传递自定义选项
      第三方插件配置
      pluginOptions: {}

      持续集成Continuous Integration
      持续集成是为了配合敏捷开发的速度和效率而产生的一个用于编译、测试、发布、部署的工具。
      持续集成哪些需要自动化
      (1)自动化的运行测试；
      (2) 自动产生可部署的二进制成品；
      (3) 自动将成品自动部署到近似生产环境；
      (4) 自动为CodeBase打上标签；
      (5) 自动运行回归测试；
      (6)自动生成度量报告

      配置环境，解决无法运行的bug，安装依赖，成功运行物联网项目；
      了解muuri插件的使用
      了解了一下slot,模块化

      git flow
      常用分支
      production分支:通常为master分支，主要用于发布生产环境的代码，所有在Master分支上的Commit应该Tag
      release分支：基于Develop分支创建，发布一个新Release，合并到Master和Develop分支
      hotfixf分支：基于Master分支创建，Production发现新的Bug时候，合并回Master和Develop分支
      develop分支：基于master分支创建，主开发分支，合并到master分支
      feature分支：基于develop分支创建，功能开发分支，合并到Develop分支

      简单理解transform:matrix(a,b,c,d,e,f)
      偏移: matrix(1, 0, 0, 1, x偏移量, y偏移量)
      缩放:matrix(x缩放倍数, 0, 0, y缩放倍数, 0, 0)
      倾斜:matrix(cosθ, sinθ, sinθ, cosθ, 0, 0)
      旋转:水平倾斜角度 = -垂直倾斜角度
      www.fabianfallend.com页面
      图片动画效果
      hover时图片放大1.1倍  transform: matrix(1, 0, 0, 1, 0, 0)->transform: matrix(1.1, 0, 0, 1.1, 0, 0)
      上下红条框y由0放大到1  transform: matrix(1, 0, 0, 0, 0, 0)->matrix(1, 0, 0, 1, 0, 0)
      左右红条框x由0放大到1  transform: matrix(0, 0, 0, 1, 0, 0)->matrix(1, 0, 0, 1, 0, 0)

  </div>
</template>

<script>

export default {
  name: 'Home',
  components: {
  }
}
</script>
