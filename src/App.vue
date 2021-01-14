<template>
  <div id="app">
    <span v-text="message"></span>
    <hr>
    <h2 v-show="isShow">Hello</h2>
    <hr>
    <h2 :key="emp.id" v-for="emp in employee">
      <span v-bind:class="emp.salary >= 90000 ? 'high' : emp.salary >= 30000 ? 'medium' : 'low'">
        {{ emp.name }}
      </span>
      <span v-if="emp.salary >= 90000">***</span>
      <span v-else-if="emp.salary >= 30000">**</span>
      <span v-else>*</span>
    </h2><br>
    <a :href="urlSKRU">SKRU</a><br><br>
    <img :src="require('@/assets/img/'+ imagesName + '.jpg')" alt="cat" width="100px" height="100px">
  </div>
</template>

<script>

export default {
  name: 'App',
  components: {
  },
  data(){
    return {
      imagesName: "cat", 
      urlSKRU: "https://www.skru.ac.th",
      message: "Hello World",
      isShow: true,
      employee: [
        {"id":1, "name":"Cat", "salary":90000},
        {"id":2, "name":"Dog", "salary":30000},
        {"id":3, "name":"Fish", "salary":10000},
      ],
    }
  },
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.high {
  color: green;
}
.medium {
  color: orange;
}
.low {
  color: red;
}
</style>
