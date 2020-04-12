# 插槽
## 插槽的内容
    可以是各个种类的
## 编译作用域
    父级模板里的所有内容都是在父级作用域中编译的；子模板里的所有内容都是在子作用域中编译的
## 后备内容
    在给出一个默认值，在没有内容时显示
## 具名插槽
    在有多个内容需要插入时:
        定义组件时：
            插入多个slot，每个都有名字
        使用时
            template作为载体，template中包含v-slot:slot-name
                slot-name是已经定义的任何slot的名称
                template可以是任何标签元素,在没有时可以用template代替，毕竟它不会加载到页面上
## 作用域插槽
    在只有默认插槽时，组件标签可以当作插槽的模板来使用
        <component-name v-slot:default="data"></component-name>
            data:父组件要传递给插槽的数据
        简写：省掉default-->v-slot="data"
### 解构插槽 Prop
        上述中的data可以直接传入对象
            对象的内容甚至可以进行自定义
## 动态插槽名
    在使用时：v-slot:[dynamicSlotName]
## 具名插槽的缩写
    v-slot:slotname可以简写成#slotname
        但是，只有在具名时可以使用，如果时默认的#="{user}"则无法使用
            默认的可以简写成#default            
## 其他示例
    <slot name="todo" v-bind:todo="todo">
      {{ todo.text }}
    </slot>
## 废弃了的语法
>就不看了先
