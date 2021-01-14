<template>
  <div id="app">
    <h1 class="title">
      Welcome to simple text editor 
    </h1>
    <Editor/>
  </div>
</template>

<script>
import Editor from './components/Editor.vue'

export default {
  name: 'App',
  components: {
    Editor
  }
}
</script>

<style>
body {
  font-family: Helvetica, sans-serif;
}

.title{
  text-align: center;
}
</style>
