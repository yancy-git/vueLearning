# 插件
## 使用插件
    通过全局方法 Vue.use() 使用插件
        需要在new Vue之前完成
        此方法会自动阻止同一个插件多次注册，即使多次调用（同一个），最后也只会注册一个该插件
        注：awesome-vue 集合了大量由社区贡献的插件和库。
## 开发插件
    这个就先喵一喵
# 过滤器
## 使用过滤器
    1.{{ message | capitalize }}
>capitalize可以时在组件选项中的filters中自定义的过滤器名称
    2.<div v-bind:id="rawId | formatId"></div>
    同上，只是引用的地方不同，一个是双花括号中，另一个是v-bind中
## 定义过滤器
    1.在组件中添加filters选项
    2.全局过滤器:Vue.filters("过滤器名称“,//逻辑函数)
>当全局过滤器和局部过滤器重名时，会采用局部过滤器。
## 过滤器串联
    {{ message | filterA | filterB }}
## 过滤器接受参数
    {{ message | filterA('arg1', arg2) }}
        filter默认有一个接受的参数message
        arg1是第二个参数，arg2是第三个参数