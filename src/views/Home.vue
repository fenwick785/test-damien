<template>
  <div class="home">
    <h1>Hello le monde</h1>

<div id="Home">
  <test-component></test-component>
</div>
  
    <ul>
    <li v-for="j in jedi" :key="j.name">
      <a href="">{{j.name}}</a>
    </li>
  </ul>
  </div>
 
</template>

<script>
// @ is an alias to /src
import axios from 'axios'
import Vue from 'vue'

Vue.component('test-component', {
 
  data: function(){
    return {
      test: 'sang'
    };
  }, 
  template: `<h3>Hello le {{test}}</h3>`,
});


export default {

  name: 'Home',
  data(){
    return{
      jedi: null
    }
  },
    mounted() {
      axios
      .get('https://swapi.dev/api/people')
      .then((response) => {
        this.jedi = response.data.results;
        console.log(this.jedi)
      });
    }
}
</script>
