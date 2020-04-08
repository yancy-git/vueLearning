    1.表单输入绑定
        1.1基础用法
            v-model 会忽略所有表单元素的 value、checked、selected attribute 的初始值
            总是将 Vue 实例的数据(data)作为数据来源

            <!-- 重要 -->
            v-model 在内部为不同的输入元素使用不同的属性并抛出不同的事件：
                text 和 textarea 元素使用 value 属性和 input 事件；
                checkbox 和 radio 使用 checked 属性和 change 事件；
                select 字段将 value 作为 prop 并将 change 作为事件。
            1.1.1
                文本、多行文本
            1.1.2
                复选框
                    单个复选框：绑定到布尔值
                    多个复选框：绑定到同一个数组
            1.1.3
                单选按钮：绑定到同一个 空字符串
                选择框 
                    单选时：绑定到空字符串
                    多选时：绑定到同一个数组,需要加上mutiple
                用 v-for 渲染的动态选项  
                结论：v-model绑定的是selected 即上述的布尔值或者同一个数组
                    
        1.2 值绑定
            把值绑定到 Vue 实例的一个动态属性上，这时可以用 v-bind 实现，并且这个属性的值可以不是字符串。
            猜想：将一个对象绑定在value，则选中时可以浏览对象的具体信息，很有用 
        1.3修饰符
            .lazy //从而转变为使用 change 事件进行同步
            .number  //自动将用户的输入值转为数值类型
            .trim //自动过滤用户输入的首尾空白字符
        1.4 在组件上使用v-model
            这里没讲，在后面的内容中