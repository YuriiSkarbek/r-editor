<template>
  <div class="editor__container">
    <div 
      class="editor" 
      contenteditable="true" 
      spellcheck="false"
      ref="editor"
      v-html="text"
    ></div>
    <Toolkit
      v-on:style-text="styleText"
      v-on:create-json="createJson"
    />
  </div>
</template>

<script>
  import Toolkit from './Toolkit.vue'
  export default {
    components: {
      Toolkit
    },
    data: {
      return() {
        text: String
      }
    },
    created() {
      this.text = '<span style="color: rgb(0, 143, 179);">Hello</span>, how about going <span style="text-decoration-line: line-through;">to cycling</span>&nbsp;for <span style="font-weight: bold;">a walk</span>? I`ll take a <span style="background-color: rgb(235, 250, 117);">boards games</span>';
    },
    methods: {
      styleText: function(style, value){
        document.execCommand("styleWithCSS", false, true);
        document.execCommand(style, false, value)
      },
      createJson: function(){
        let jsonData = {
          textEl: []
        };
        let childNodes = this.$refs.editor.childNodes;
        console.log(childNodes.length);
        for(let i = 0; i < childNodes.length; i++){
          if(childNodes[i].nodeName === "#text"){
            jsonData.textEl.push({
              text: childNodes[i].nodeValue,
              color: "#000",
              bgColor: "#fff",
              fontSize: "16px",
              fontWeight: "normal",
              fontStyle: "normal",
              textDecoration: "none"
            });
          } else {
            jsonData.textEl.push({
              text: childNodes[i].textContent,
              color: childNodes[i].style.color ? childNodes[i].style.color : "#000",
              bgColor: childNodes[i].style.backgroundColor ? childNodes[i].style.backgroundColor : "#fff",
              fontSize: childNodes[i].style.fontSize ? childNodes[i].style.fontSize : "16px",
              fontWeight: childNodes[i].style.fontWeight ? childNodes[i].style.fontWeight : "normal",
              fontStyle: childNodes[i].style.fontStyle ? childNodes[i].style.fontStyle : "none",
              textDecoration: childNodes[i].style.textDecorationLine ? childNodes[i].style.textDecorationLine : "none"
            });
          }
        }
        console.log(jsonData.textEl);
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .editor__container{
    width: 564px;
    height: auto; 
    border: 1px solid #ccc;
    margin: 0 auto;
  }

  .editor {
    width: 100%;
    min-height: 100px;
    padding: 12px;
    box-sizing: border-box;
    outline: none;
  }

</style>