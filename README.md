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

