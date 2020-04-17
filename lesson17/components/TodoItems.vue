<template>
    <ul v-if="items.length">
        <li v-for="(item,index) in items" :key="item">
            {{item}}
            <button 
                @click="$emit('removeItem',index)"
            >
                x
            </button>
        </li>
    </ul>
    <p v-else>没有任何要做的</p>
</template>
<script>
export default {
    props:{
        items:{
            type:Array,
            required:true
        }
    }
}
</script>