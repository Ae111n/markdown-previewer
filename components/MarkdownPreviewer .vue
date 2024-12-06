<template>
  <div id="main">
    <fieldset>
      <legend>markdown</legend>
      <textarea class='blackboard' placeholder="your markdown goes here" id="editor" v-model="input"></textarea>
      <button id="clear-button" class="button-clear" @click="clearTextArea">Clear textArea</button>
    </fieldset>

    <fieldset>
      <legend>preview</legend>
      <div id="preview" v-html="parseMarkdown"></div>
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
    clearTextArea() {
      this.input = ''
    }
  },
  computed: {
    parseMarkdown() {
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
  font-family: "Open Sans", sans-serif;
}

fieldset {
  border: none;
  min-width: 550px;
  width: 75%;
  min-height: 280px;
  margin: auto;
}

legend {
  color: rgb(58, 25, 96);
  font-size: 22px;
  font-style: italic;
  font-weight: bold;
  margin-bottom: -30px;
  border-radius: 5px;
  padding-bottom: 25px;
  padding-left: 10px;
  padding-right: 10px;
  padding-top: 2px;
  box-shadow: rgba(50, 50, 93, 0.25) 0px 50px 100px -20px,
    rgba(0, 0, 0, 0.3) 0px 30px 60px -30px,
    rgba(10, 37, 64, 0.35) 0px -2px 6px 0px inset;
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

.blackboard:focus {
  outline: none;
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

.button-clear {
  font-family: "Open Sans", sans-serif;
  font-size: 20px;
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
  float: right;
  margin-right: auto;
}

.button-clear:active {
  box-shadow: 0px 0px 0px 0px;
  top: 5px;
  left: 5px;
  margin-top: 0;
}

@media (max-width: 668px) {
  .button-clear {
    padding: 0.25em 0.75em;
    float: right;
    margin-right: 100px;
    font-size: 16px;
  }

  #editor {
    min-width: 160px;
    width: 80%;
    min-height: 180px;
    border-left: 9px solid rgb(95, 47, 151);
    border-top: 9px solid rgb(78, 36, 126);
    border-right: 9px solid rgb(58, 25, 96);
    border-bottom: 9px solid rgb(46, 16, 81);
    box-shadow: 8px 7px 15px rgb(101, 97, 86);
    background-color: rgb(29, 29, 29);
    color: white;
  }

  #preview {
    min-width: 160px;
    width: 80%;
    min-height: 180px;
    border-left: 9px solid rgb(95, 47, 151);
    border-top: 9px solid rgb(78, 36, 126);
    border-right: 9px solid rgb(58, 25, 96);
    border-bottom: 9px solid rgb(46, 16, 81);
    box-shadow: 8px 7px 15px rgb(101, 97, 86);
    background-color: rgb(0, 0, 0);
    color: white;
  }
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