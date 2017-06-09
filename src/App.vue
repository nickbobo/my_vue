<template>
  <div id="app">
    <img src="./assets/logo.png">
    <h1>{{ msg }} {{name}}</h1>

    <span v-bind:title="status">
      鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span>
    <span v-if="status">
      鼠标悬停几秒钟查看此处动态绑定的提示信息！
    </span>
    
    <ul>
      <li v-for="todo in todos">
        {{ todo.text }}
      </li>
    </ul>


    <div>
      <p>{{ message }}</p>
      <button v-on:click="reverseMessage">逆转消息</button>
    </div>


    <div id="app-6">
      <p>{{ message }}</p>
      <input v-model="message">
    </div>

    <ol>
      <!-- 创建一个 todo-item 组件的实例 -->
      <todo-item></todo-item>
    </ol>
  </div>
</template>

<script>


export default {
  name: 'app',

  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      name:'bobo',
      status:false,
      todos: [
        { text: '学习 JavaScript' },
        { text: '学习 Vue' },
        { text: '整个牛项目' },
      ],
      message: 'Hello Vue.js!',
      template: '<todo-item></todo-item>'
    }
  },  
  methods: {
    reverseMessage () {
      console.info(111);
      this.message = this.message.split('').reverse().join('')
    }
  }
}


</script>

<style lang="scss">
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
