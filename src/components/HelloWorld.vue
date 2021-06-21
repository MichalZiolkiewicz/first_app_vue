<template>
  <div class="hello">
    <p v-if="counter >= 3 && counter <= 9">Hejka {{ name }}</p>
    <p> Punkty: {{ counter }} </p>
    <button v-on:click="addToCounter">+1</button>
    <button v-if="counter > 0" v-on:click="counter--">-1</button>
    <ul>
      <li v-bind:key="user.id" v-for="user in users">User {{ user.name }}, at age {{ user.age }} </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String,
  },
  data: function () {
    return {
      name: 'Michał',
      counter: 0,
      users: [
        {name: 'Michał', age: 24, id: 1},
        {name: 'Julka', age: 23, id: 2},
        {name: 'Tomek', age: 20, id: 3}
      ]
    }
  },
  methods: {
    addToCounter() {
      this.counter++
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
