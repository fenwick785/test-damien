<template>
  <div class="people">
    <h1>Hello le monde</h1>

    <ul id="liste">
    <li v-for="j in jedi" :key="j.name">
      {{j.name}}
    </li>
  </ul>
  </div>
 
</template>

<script>
// @ is an alias to /src
import axios from 'axios'

export default {

  name: 'People',
 
}
</script>