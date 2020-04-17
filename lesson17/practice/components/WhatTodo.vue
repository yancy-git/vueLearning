<template>
    <div>
        <ul v-if="items.length">
            <li v-for="(item,index) in items" :key="index">
                {{item}}
                <button
                    @click="$emit('delThis',index)"
                >
                    搞定
                </button>
            </li>
        </ul>
        <p v-else>放假了</p>
    </div>
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