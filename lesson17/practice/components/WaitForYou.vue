<template>
    <div>
        <!--  添加待办事项的输入框-->
        <TodoInput v-model="todoInput" @keydown.enter="addThis"></TodoInput>
        <!-- 待办事项显示 -->
        <WhatTodo :items="items" @delThis="delThis"></WhatTodo>
    </div>
</template>
<script>
import TodoInput from './TodoInput'
import WhatTodo from './WhatTodo'

export default {
    components:{
        TodoInput,WhatTodo
    },
    data:function(){
        return {
            todoInput:"",
            items:[
            ]
        }
    },
    methods:{
        addThis(){
            this.items.push(this.todoInput)
            this.todoInput=""
        },
        delThis(value){
            this.items.splice(value,1)
        }
    }
}
</script>