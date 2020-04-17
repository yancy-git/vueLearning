# 可复用性&组合
##  混入
>声明一个对象，这个对象可以包括任意组件选项，然后组件可以使用这个对象，称之为混入
### 混入的原则
    1.组件和混入对象含有同名选项时：合并，发生冲突时以组件数据优先
        混入对象data中：msg="混入msg"
        组件data中：msg="组件msg"
        组件使用混入对象之后，msg="组件msg"
    2.同名的钩子函数：合并为数组
        调用时优先度：混入对象的狗子 > 组件的狗子
    3.值为对象的选项，例如mthodds,components：合并为一个对象
        对象键名冲突时：取组件的键值对
>Vue.extend() 也使用同样的策略进行合并
### 全局混入
    慎用，会影响到所有之后创建的Vue实例
>这里注意，是之后 之后，之后，之前创建的不受影响
###  选项合并策略 可以进行自定义
        向 Vue.config.optionMergeStrategies 添加一个函数
            例如,使myoptions的合并策略改为和mthods相同的合并策略：
            var strategies = Vue.config.optionMergeStrategies
            strategies.myOptions = strategies.methods

## 自定义指令
>和组件类似，要使用自定义指令，必须先注册一个自定义指令
### 注册自定义指令
    1.全局自定义指令：
> 全局自定义指令，使用v-指令名进行绑定，例如这里，绑定的元素会在加载完成时自动获得焦点
        Vue.directive("指令名",{
>这里的inserted指 被绑定的元素插入到DOM中时
            inserted:function(el){
                // 聚焦元素
                el.focus()
            }
        })
    2.局部自定义指令：
        在组件内部，可以增加一个directive的选项
            这个指令就直接绑定给这个组件了
### 自定义指令可选的钩子函数
>在自定义指令时可以提供的钩子函数（均为可选）
    bind 只调用一次，指令第一次绑定到元素时调用。在这里可以进行一次性的初始化设置。
    inserted 被绑定元素插入父节点时调用
    update 所在组件的 VNode 更新时调用
    componentUpdated 指令所在组件的 VNode 及其子 VNode 全部更新后调用。
    unbind 调用一次，指令与元素解绑时调用。
### 钩子函数的参数
>除了el之外，其他的参数均为只读，切勿修改
    el 指令所绑定的元素，可以用来直接操作 DOM。
    binding  包含很多属性
    vnode
    oldVnode 仅在 update 和 componentUpdated 钩子中可用。
#### 动态指令参数：
        指令的参数可以是动态的。例如，在 v-mydirective:[argument]="value"
            argument可以根据组件实例数据进行更新
### 对象字面量
    <div v-demo="{ color: 'white', text: 'hello!' }"></div>

## 渲染函数 & JSX
    render:function(createElement){
        return createElement("标签名",内容)
    }
### 虚拟DOM
    上述的render返回的是一个虚拟DOM（virtual node）,也称VNode
## 熟悉createElement参数
### 深入数据对象
    了解可以绑定的一些属性
### 约束
    组件树中的所有 VNode 必须是唯一的
    如果你真的需要重复很多次的元素/组件，你可以使用工厂函数来实现（map）
## 使用 JavaScript 代替模板功能
    了解了一下
## JSX
    使用Babel插件，在Vue中使用JSX语法时，语法更接近Vue的模板的语法
## 函数式组件
>因为函数式组件只是函数，所以渲染开销也低很多
>函数式组件的内容要相对于一般的组件精简很多props不需要声明，直接绑定在content对象中，this.$slots包含在context.children中
>具体使用时可以通过控制台具体变动
### 向子元素或子组件传递 attribute 和事件
    让组件函数化： functional: true,
    render:除了createElement之外，还需要增加一个context参数
        context参数包含了很多东西
