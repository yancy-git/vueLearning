1.绑定html类
    支持三种格式：
        1.1对象语法
            <div v-bind:class="{ active: isActive }"></div>
        1.2数组语法
            <div v-bind:class="[activeClass, errorClass]"></div>
        1.3带组件
            <!-- 自定义组件 -->
            Vue.component('my-component', {
                template: '<p class="foo bar">Hi</p>'
            })
            <!-- 使用組件 -->
            <my-component class="baz boo"></my-component>
            <!-- 呈现的效果 -->
            <p class="foo bar baz boo">Hi</p>
2.绑定内联样式
    支持：
        2.1对象语法
        2.2数组语法
        2.3自动前缀：
            <!-- 没怎么搞懂 -->
            当您使用需要一个CSS属性供应商前缀的v-bind:style，例如transform，Vue公司会自动检测并添加适当的前缀到应用的样式
        2.4多个值
            <!-- 从2.3.0+开始 -->
            <div v-bind:style="{ display: ['-webkit-box', '-ms-flexbox', 'flex'] }"></div>
3.带条件的渲染
    <!-- 使用v-if -->
        <h1 v-if="awesome">Vue is awesome!</h1>
    <!-- 也可以通过以下方式添加“其他块” v-else： -->
        <h1 v-if="awesome">Vue is awesome!</h1>
        <h1 v-else>Oh no 😢</h1>
    v-else
        一个v-else元素必须紧跟一个v-if或一个v-else-if元素-否则将无法识别。
    v-else-if
        与v-else相似，v-else-if元素必须紧随v-if或v-else-if元素。
4.v-show和v-if的区别
    都可以控制元素的显示
    不同的是：v-if不成立时元素直接删除
            v-show不成立时,只是修改的dispaly属性，元素还存在，只是看不见
    请注意，v-show它不支持<template>元素，也不支持v-else。
5.v-if 与 v-for
    不推荐一起使用，v-for的优先级要高于v-if
6.v-for进行列表渲染
    <li v-for="item in items" :key="item.message">{{item.msg}}</li>
    <!-- 进行v-for时，加上唯一的key,在进行排序等操作时就不需要销毁创新节点了，这句话没懂先记着 -->
    v-for中的in  可以使用 of 来代替，这样的语法是为了更贴合js迭代语法
    <!-- 重要 -->
    v-for建议尽可能提供一个key属性，除非迭代的DOM内容很简单，或者您有意依赖默认行为来获得性能。
7.vue中也封装了对数组的操作
    <!-- 变异方法 :会是数组发生改变-->
    push() //往数组最后面添加一个元素，成功返回当前数组的长度
    pop() //删除数组的最后一个元素，成功返回删除元素的值
    shift() //删除数组的第一个元素，成功返回删除元素的值
    unshift() //往数组最前面添加一个元素，成功返回当前数组的长度
    splice()：
        三个参数：
            第一个是想要删除的元素的下标（必选），
            第二个是想要删除的个数（必选），
            第三个是删除 后想要在原位置替换的值（可选）
    sort() // 使数组按照字符编码默认从小到大排序,成功返回排序后的数组
    reverse() //将数组倒序，成功返回倒序后的数组
    <!-- 非变异方法：不会改变原始数组，而是产生一个新的数组 -->
    filter() //按照某种规则来过滤数组中的元素
    concat() //拼接数组，可以拼接值，也可以拼接另一个数组，也可以拼接两个：arr1.concat(arr2,arr3)
    slice() //返回数组中的元素：slice(start,end)，其中不包括index=end的元素
8.显示筛选/排序结果
    无需改动原始数据，可以添加一个计算属性computed
    例如一个数组 number,使用computed获得偶数evenNumer,然后将evenNumber进行显示
9.v-for也可以取整数
    <!-- 循环模板10次 -->
     <span v-for="n in 10">{{ n }} </span>
    <!-- 结果 -->
    1 2 3 4 5 6 7 8 9 10