<template>
  <div>
    <h1>Select An Ipsum To Preview:</h1>
    <ul>
      <li 
          v-for="ipsum in ipsumList"
          v-bind:key="ipsum.title"
          v-on:click="$emit('select', ipsum)"
          v-bind:class="['ipsum', { selected: ipsum === selected }]"
      >
      {{ ipsum.title }}
      </li>
    </ul>
  </div>
</template>

<script>
import ipsumList from '../data.js';

export default {
  data() {
    return { ipsumList };
  },
  props: ['selected']
};
</script>

<style>
@import url('https://fonts.googleapis.com/css?family=Neuton');
h1 {
  padding: 10px 20px;
}

.ipsum {
  cursor: pointer;
}

li:hover {
  color: antiquewhite;
  background-color: #9e0470;
}


</style>