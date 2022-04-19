<template>
  <div class="hello">
  <h1>Something</h1>
    <h1>{{ msg }}</h1>
    <h1>{{store.counter}}</h1>
      <h1>{{store.name}}</h1>
      <h2>{{store.dblcount}}</h2>

      <button @click="store.counter++ ">click me</button>&emsp;&emsp;
      <button @click="dec" >Decrement</button>

      &emsp;&emsp;<button @click="store.counter=0">Reset</button>
    

  </div>
</template>

<script >
import {useStore} from '../stores/pinia'
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  setup(){
    const store=useStore();
    store.$patch({
      counter:0,
      name:'Sonu Rathaur'
    })
    return {store}
  },
  methods:{
    dec(){
      this.store.increment();
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
