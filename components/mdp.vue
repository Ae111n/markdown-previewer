<template>
  <div id="main">
    <fieldset>
      <legend>markdown</legend>
      <textarea class='blackboard' placeholder="your markdown goes here" id="editor" v-model="input"></textarea>
    </fieldset>

    <button id="clearbtn" class="button-54" @click="clearta">Clear textArea</button>

    <fieldset>
      <legend>preview</legend>

      <div id="preview" v-html="parsemd"></div>
    </fieldset>
  </div>
</template>

<script>
import { marked } from 'marked'
export default {
  data() {
    return {
      input: " # FCC markdown previewer",
    }
  },
  methods: {
    clearta() {
      this.input = ''
    }
  },
  computed: {
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

}

fieldset {
  border: 0px;
  min-width: 550px;
  width: 75%;
  min-height: 280px;
  margin: auto;
}

legend {
  color: rgb(58, 25, 96);
  ;
  font-size: 22px;
  font-style: italic;
  margin-bottom: -5px;
}

#editor {
  min-width: 550px;
  width: 100%;
  min-height: 280px;
  margin-bottom: 8px;
  border-left: 11px solid rgb(95, 47, 151);
  border-top: 11px solid rgb(78, 36, 126);
  border-right: 11px solid rgb(58, 25, 96);
  border-bottom: 11px solid rgb(46, 16, 81);
  box-shadow: 10px 8px 19px rgb(101, 97, 86);
  background-color: black;
  color: white;
}


#preview {
  min-width: 550px;
  width: 100%;
  min-height: 280px;
  border: 1px solid grey;
  background-color: rgb(0, 0, 0);
  color: white;
  border-left: 11px solid rgb(95, 47, 151);
  border-top: 11px solid rgb(78, 36, 126);
  border-right: 11px solid rgb(58, 25, 96);
  border-bottom: 11px solid rgb(46, 16, 81);
  box-shadow: 10px 8px 19px rgb(101, 97, 86);
  margin-top: 0px;
}






.button-54 {
  font-family: "Open Sans", sans-serif;
  font-size: 16px;
  letter-spacing: 2px;
  text-decoration: none;
  text-transform: uppercase;
  color: #000;
  cursor: pointer;
  border: 3px solid;
  padding: 0.25em 0.5em;
  box-shadow: 1px 1px 0px 0px, 2px 2px 0px 0px, 3px 3px 0px 0px, 4px 4px 0px 0px, 5px 5px 0px 0px;
  position: relative;
  user-select: none;
  -webkit-user-select: none;
  touch-action: manipulation;
}

.button-54:active {
  box-shadow: 0px 0px 0px 0px;
  top: 5px;
  left: 5px;
}

@media (min-width: 768px) {
  .button-54 {
    padding: 0.25em 0.75em;
  }
}

#main {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
}

#__layout {
  display: flex;
  align-items: center;
  justify-content: center;
}

html {
  height: 100%;
  width: 100%;
  background-color: rgb(180, 186, 199);

}
</style>