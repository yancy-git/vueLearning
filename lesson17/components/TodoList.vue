<template>
    <div>
        <TodoInput 
            v-model="nextTodo"
            @keydown.enter="addTodo"
        ></TodoInput>
        <TodoItems 
            :items="items" 
            @removeItem="removeItem" 
        ></TodoItems>
    </div>
</template>

<script>
import TodoInput from './TodoInput'
import TodoItems from './TodoItems'

export default {
    components:{
        TodoInput,
        TodoItems
    },
    data:function(){
        return {
            nextTodo:"",
            items:[
                "洗脸"
            ]
        }
    },
    methods:{
        removeItem(index){
            this.items.splice(index,1)
        },
        addTodo(){
            this.items.push(this.nextTodo);
            this.nextTodo=''
        }
    }
}
</script>