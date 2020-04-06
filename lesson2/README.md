第二天：
    1.创建Vue实例：
        var vm = new Vue()//创建一个实例对象,其中可以有data
            Object.freeze(vm)
                //freeze方法可以冻结对象，防止更改现有属性
                //vm.$el可以获取对应的dom,和js中根据id获取dom类似（我的理解）
            vm.$watch('a',function(newValue,oldValue){})
                //$watch方法可以具体制定到某个数据，观察他的变化
            vm.$off('a')
                //移除监听事件
    2.实例生命周期挂钩
        //提供了各种不同的阶段，可以在特定阶段添加自己的代码
        完整周期：beforeCreate
                created
                beforeMount //安装之前
                mounted     //已安装

                beforeUpdate
                updated

                beforeDestroyed
                destroyed
    3.插值
        <span>Message: {{ msg }}</span>
            //双花括号进行文本插值
        v-once指令执行一次性插值，该插值不会更新
    4.原始HTML
        data中msg:"<p>5555</p>"
            <p>message:{{msg}}</p>---//输出<p>5555</p>
            <p><span v-html="msg"></span></p>---//输出5555
    5.属性
        HTML属性内不能使用胡须(id="xxx")
        要使用v-bind指令
        在使用v-bind指令时：
            disabled的值null，undefined或者false： 
                disabled属性直接消失，也就是审查元素也找不到该属性
    6.使用JavaScript表达式
        每个绑定只能包含一个单一的表达（这个也不知道怎么写）
    7.指令
        v-if指令将<p>根据表达式值的真实性删除/插入元素seen
            true:元素显示
            false:审查不到元素
    8.动态参数
        从版本2.6.0开始支持：
            <a v-bind:[attributeName]="url"> ... </a>
                attributeName（其值为）"href"，则此绑定将等效于v-bind:href
            <a v-on:[eventName]="doSomething"> ... </a>
        上述例子中的attributeName以及eventName：
            值可以是null,这是绑定的属性将被删除
                任何其他非字符串值(比如false,undefined)都将触发警告
        动态参数约束：
            例如空格和引号无效：
                <a v-bind:['foo' + bar]="value"> ... </a>
            解决方法：（还没有例子）
                使用不带空格或引号的表达式，或者将复杂表达式替换为计算属性
        应避免使用大写字母命名键:
            浏览器会将属性名称强制转换为小写字母
                示例：<a v-bind:[someAttr]="value"> ... </a>
    9.修饰符
        修饰符是用点表示的特殊后缀，表示应以某种特殊方式绑定指令
            <form v-on:submit.prevent="onSubmit"> ... </form>
                告诉v-on指令调用event.preventDefault()
    10.简写
        v-bind简写为":"
            <a :href="url"> ... </a>
        v-on简写为"@"
            <a @click="doSomething"> ... </a>
    