# 深入了解组件
## 组件注册
### 组件名
#### 组件名大小写规则：
    1.驼峰命名
    2.全小写，单词之间使用"-"进行分割
### 全局注册
    使用Vue.component进行全局注册，可以用在任何根实例模板中
### 局部注册
>TODO:模块系统
## Prop
>在使用定义的模板时，最好全部用"-"进行单词分割
### prop类型
    每个prop可以指定类型可以给定一个类型，也可以给定一个类型数组
### 传递静态或动态的prop
    prop可以传递
        数字、布尔值、数组、对象、一个对象的所有属性
### 单向数据流
    1.子组件接收prop，希望保留作为数据data:最好定义一个本地的data接收这个prop作为其初始值
    2.prop的值需要进行转换时：使用这个prop的值定义一个computed属性
### prop验证
    1.可以定义一种检查类型
    2.使用数组来定义多个可能的类型
>表示必填的字符串
    3.propc:{
        type:String,
>type可以是String\Number\Boolean\Array\Object\Date\Function\Symbol
>还可以是一个自定义的构造函数，例如定义一个Person构造函数,使用prop-name:Person来验证prop-name是否是通过Person创建的
        required:true
>设置默认值,根据定义的type来决定类型
        default:“默认字符串”
>甚至可以默认对象
        default:function(){
            return {key:value}
        }
    }
    4.自定义验证函数
>当 prop 验证失败的时候，(开发环境构建版本的) Vue 将会产生一个控制台的警告
>注意那些 prop 会在一个组件实例创建之前进行验证，所以实例的属性 (如 data、computed 等) 在 default 或    validator 函数中是不可用的。
### 非 Prop 的 Attribute
    直接将Attribute添加到组件实例上
#### 替换/合并已有的 Attribute
    当在模板内部和组件实例同时定义了一个Attribute
        1.掉模板中的Attribute会被父级组件中的替换
        2.class和style两种属性，会合并
#### 禁用 Attribute 继承
        这尤其适合配合实例的 $attrs 属性使用
        有了 inheritAttrs: false 和 $attrs，你就可以手动决定这些 attribute 会被赋予哪个元素
>注意 inheritAttrs: false 选项不会影响 style 和 class 的绑定。        