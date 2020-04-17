<template>
    <input 
        type="text"
        v-on="listeners"
        :value="value"
        placeholder="输入待办事项后点击回车加入任务列表"
    >
</template>
<script>
export default {
    props:{
        value:{
            type:String,
            required:true
        }
    },
    computed:{
        listeners:function(){
            return {
                ...this.$listeners,
                input:event => this.$emit('input',event.target.value)
            }
        }
    }
}
</script>