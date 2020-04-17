# 单文件组件
    主要是组件中包含组件
    难点：如何在脚手架的模式下进行开发
---------
## 总结：
1. 组件中包含组件:
    1.1 在script中进行引入-->import
    1.2 在export default中components属性中添加该组件名称
2. data是组件中的data，要写成function的形式，不然控制台回警告
3. input在组件中，需要绑定value属性，并在props中声明value
    但不同的是，使用组件时不需要再对vaue进行绑定---value自动绑定为input的value
4. v-on="listeners"
    在计算属性中声明listener函数
>  ...this.$listeners  这一句没懂，大概就是获取父组件啥啥啥的
    input: event => this.$emit('input',event.target.value)
>  这里有个this注意一下