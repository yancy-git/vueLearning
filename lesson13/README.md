# 过渡 & 动画
## 进入/离开 & 列表过渡
### 概述
    Vue 在插入、更新或者移除 DOM 时,有多种不同方式的应用过度效果：
        1.在 CSS 过渡和动画中自动应用 class
        2.可以配合使用第三方 CSS 动画库，如 Animate.css
        3.在过渡钩子函数中使用 JavaScript 直接操作 DOM
        4.可以配合使用第三方 JavaScript 动画库，如 Velocity.
### 单元素/组件的过渡
#### 在进入/离开的过渡中，会有 6 个 class 切换,enter和leave各三个:
        enter, enter-active, enter-to
        leave, leave-active, leave-to
    如果使用一个没有名字的 <transition> ,类名的前缀为v-
    如果定义了transition的name,那么类名v-enter变为name-enter，其他类名同理
>这动画搞的人有点晕，先放着