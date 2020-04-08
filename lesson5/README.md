vue学习第五课：2020.4.8
    1.事件处理
        监听事件：
            可以用 v-on 指令监听 DOM 事件
                例如v-on:click可以简写@click
                    <!-- 这里前面的小例子已经联系过了，简略的过一遍 -->
    2.内联处理器中的方法:
        2.1其实就是调用方法的同时传入一个参数
        2.2有时也需要在内联语句处理器中访问原始的 DOM 事件。可以用特殊变量 $event 把它传入方法
            @click=xxx(参数1，$event)
                <!-- $event是一个参数，通过这个参数我们可以访问到原生事件对象 -->
                <!-- 例如，event.preventDefault() 阻止默认事件 -->
    3.事件修饰符
        .stop   // 阻止事件继续传播 即阻止它的捕获和冒泡过程
        .prevent //阻止默认事件发生 即event.preventdefault():
        .capture // 添加事件监听器时使用事件捕获模式，即在捕获模式下触发
        .self //当前元素自身时触发处理函数时才会触发函数
        .once .once //只触发一次
        .passive //不要把 .passive 和 .prevent 一起使用       
        <!-- 使用修饰符时，顺序很重要 -->
    4.按键修饰符
        <!-- 只有在 `key` 是 `Enter` 时调用 `vm.submit()` -->
            <input v-on:keyup.enter="submit">  
    5.按键码
        keyCode 的事件用法已经被废弃了并可能不会被最新的浏览器支持。
        为了在必要的情况下支持旧浏览器，Vue 提供了绝大多数常用的按键码的别名：
        如果你想支持 IE9，使用内置的别名应该是首选。
        你还可以通过全局 config.keyCodes 对象自定义按键修饰符别名：
    6.系统修饰键
        .ctrl
        .alt
        .shift
        .meta //对应window按键
        <!-- 请注意修饰键与常规按键不同,,件触发时修饰键必须处于按下状态 -->
    7.修饰符
        .exact 修饰符允许你控制由精确的系统修饰符组合触发的事件。
                <!-- 即使 Alt 或 Shift 被一同按下时也会触发 -->
                <button @click.ctrl="onClick">A</button>

                <!-- 有且只有 Ctrl 被按下的时候才触发 -->
                <button @click.ctrl.exact="onCtrlClick">A</button>

                <!-- 没有任何系统修饰符被按下的时候才触发 -->
                <button @click.exact="onClick">A</button>
    8.鼠标按钮修饰符
                .left
                .right
                .middle    
