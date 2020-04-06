2020.4.6开始练习vue
    每天的代码使用github更新版本，方便以后复习
    第一天：
    1.声明式渲染：
        指令：v-bind:title(鼠标悬停显示提示文本)
    2.条件和循环:
        条件：控制元素的存在
            v-if="data中的某个属性，例如seen"
                seen：true则元素存在页面
                    false则不存在
        循环：遍历数组
            v-for="todo in todos"
                todo为形参 
                todos为数组
        即时添加元素：
            在控制台中执行：app4.todos.push({ text: 'New item' })
                页面上动态的加载最新的数据
    3.处理用户输入：
        使用v-on指令附加事件侦听器：
            v-on:click="reverseMessage"
                reverseMessage：函数名（在methods中指定,自定义）
        双向绑定：
            v-model="message"
                例如input绑定这个指令, 则文本框中的内容就是data中的message