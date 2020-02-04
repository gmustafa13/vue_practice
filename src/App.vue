<template>
  <div id="app">
    <div>
      {{ massage }}
    </div>
    <div>
      <span v-bind:title="massage">
        hi gulam mustafa jhjhjkh
      </span>
    </div>
    <div>
      <p v-if="gulam">if directive check</p>

      <!-- <pre>{{todos}}</pre> -->
      <div>
        <ol>
          <li v-for="(x, index) in todos" :key="index">
            {{ x.name }}{{ index }}
          </li>
        </ol>
      </div>

      <div>
        <p>{{ massage }}</p>
        <button @click="firstfunction()">reverse massage</button>
      </div>
    </div>
    <div>
      <p>
        <input type="text" v-model="massage">
      </p>
    </div>
    <p>{{info}}</p>
    <div>
      <helloWorld  v-for='(todo,index) in todos' :key='index'>
      
      </helloWorld>
    </div>
    <img alt="Vue logo" src="./assets/logo.png" />
  </div>
  
</template>

<script>
// import Vue from 'vue'
import axios from 'axios'
import helloWorld from '@/components/helloWorld.vue'

export default {
  components:{
helloWorld
  },
  data() {
    return {
      massage: "hellow vue",
      info:null,
      gulam: true,
      todos: [
        {
          name: "gulam",
          age: 27,
          gender: "M"
        },
        {
          name: "mustafa",
          age: 24,
          gender: "M"
        },
        {
          name: "nayan",
          age: 27,
          gender: "M"
        },
        {
          name: "dimple",
          age: 20,
          gender: "F"
        }
      ]
    };
  },
  methods: {
    firstfunction: function() {
      this.massage = this.massage
        .split("")
        .reverse()
        .join("");
    }
  },
  mounted(){
    axios
      .get('https://api.coindesk.com/v1/bpi/currentprice.json')
      .then(response => (this.info = response))
  }
  
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
