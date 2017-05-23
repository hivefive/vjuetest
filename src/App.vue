<template>
  <div id="app">
    <img src="./assets/logo.png">
    <my-nav>
      <a class="nav-item is-tab" v-for="page in pages" @click="currentScreen=page.route" :class="{ 'is-active': currentScreen==page.route }">{{ page.title }}</a>
    </my-nav>
    <component :is="currentScreen" :myList="myList" :messages="messages">Vue component</component>
    <todo-input :messages="messages" :myList="myList"></todo-input>
  </div>
</template>

<script>
import Message from './components/Message.vue';
import Nav from './components/Nav.vue';
import About from './components/About.vue';
import Home from './components/Home.vue';
import TodoInput from './components/TodoInput.vue';
import Quote from './components/Quote.vue';

export default {
  name: 'app',
  components: {
    "messagePage": Message,
    "myNav": Nav,
    "about": About,
    "home": Home,
    "todoInput": TodoInput,
    "quote": Quote
  },
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      pages: [
        {title: "Home", route: "home" },
       {title: "About", route: "about" },
       {title: "Messages", route: "message-page"},
       {title: "Quotes", route: "quote"}
       ],
      currentScreen: "home",
      messages: [{
            messageTitle: "Message Header", messageText: "This is a message that contains some text the arguably has not point other than being some text really."
          }, { 
            messageTitle: "Another Message Header", messageText: "This is an message that contains some text the arguably has not point other than being some text really." 
      }],
      myList: ["Get git", "Git gud", "Gud fanns", "Fanns Vue?"]
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
