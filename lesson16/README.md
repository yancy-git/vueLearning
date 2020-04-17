# 单文件组件
>   为什么要对单文件组件进行介绍？是为了解决一下几个问题：
1.  全局定义 (Global definitions) 强制要求每个 component 中的命名不得重复
2.  字符串模板 (String templates) 缺乏语法高亮，在 HTML 有多行的时候，需要用到丑陋的 \
3.  不支持 CSS
4.  没有构建步骤 (No build step) 限制只能使用 HTML 和 ES5 JavaScript，而不能使用预处理器，如Pug    (formerly Jade) 和 Babel
    具体查看这个图片：[https://cn.vuejs.org/images/vue-component.png]
-----
    使用之后：
        1. 完整语法高亮
        2. CommonJS 模块
        3. 组件作用域的 CSS
        具体：[https://cn.vuejs.org/images/vue-component-with-preprocessors.png]
# 怎么看待关注点分离？
    