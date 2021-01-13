<template>
  <div class="editor__container">
    <div 
      class="editor" 
      contenteditable="true" 
      spellcheck="false"
    > {{ text }} </div>
    <Toolkit
      v-on:style-text="styleText"
    />
  </div>
</template>

<script>
  import Toolkit from './Toolkit.vue'
  export default {
    components: {
      Toolkit
    },
    props: {
      text: String
    },
    methods: {
      styleText: function(style, value){
        console.log('Style Text: ', style, ' | ', value);
        document.execCommand("styleWithCSS", false, true);
        document.execCommand(style, false, value)
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .editor__container{
    width: 500px;
    height: auto; 
    border: 1px solid #ccc;
    margin: 0 auto;
  }

  .editor {
    width: 500px;
    min-height: 100px;
    padding: 12px;
    box-sizing: border-box;
    outline: none;
  }

</style>