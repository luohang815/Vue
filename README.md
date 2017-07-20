# Vue
Learn how to use Vue.js


//父组件向子组件传递数据
<div id="app">
   <input v-model="sendMsg">
   <hr/> 
   <child v-bind:get-msg='sendMsg'></child>  //注意点  ：get-msg 不能写成 ：getMsg
   // v-bind:get-msg='sendMsg' 意思是：将父组件的sendMsg 绑定给子组件，子组件通过 props 来接收
</div>


new Vue({
    el: '#app',
    data: {
        sendMsg: 'I am father ,you are my son ! Do you understand?'
    },
    components: {
        Child: {
            props: ['getMsg'],
            template: '<span>I get my father's message,He say：{{getMsg}}</span>'
        }
    }
})


总结：
   子组件中需要以某种方式例如点击事件的方法来触发一个自定义事件
   将需要传的值作为$emit的第二个参数，该值将作为实参传给响应自定义事件的方法
   在父组件中注册子组件并在子组件标签上绑定对自定义事件的监听
   
   
   http://www.cnblogs.com/daiwenru/p/6694530.html
