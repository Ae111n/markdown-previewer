<template>
  <div id="main">

    <h1>fcc markdown previewer</h1>
    <textarea placeholder="your markdown goes here" id="editor" v-model="input"></textarea>
<button id="clearbtn" @click="clearta">Clear textArea</button>
    <div id="preview" v-html="parsemd">

    </div>

  </div>
</template>

<script>
import {marked} from 'marked'
export default {
data() {
    return {
        input :" # type markdown here ",


    }
},
methods :{
clearta () {
  this.input = ''
}
},
computed :{
parsemd() {
  return marked(this.input)
}


},





}
</script>

<style>
#main {
width: 100%;
height: 100%;
display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 4px;
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
  background: fixed;

  
}
#editor {
 min-width:70%;
   max-width: fit-content ;   
    min-height:90px;

}
#preview {
    min-width:70%;
   max-width: fit-content ;   
    min-height:90px;
    border: 1px solid black;
}
#clearbtn {
  height: 44px;
  min-width:70%;
  font-size: large;
  }
</style>