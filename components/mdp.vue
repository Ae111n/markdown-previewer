<template>
  <div id="main">

    <h1>fcc markdown previewer</h1>
    <textarea  id="input"></textarea>
    <div id="output"></div>

  </div>
</template>

<script>
export default {

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
#input {
 min-width:70%;
   max-width: fit-content ;   
    min-height:90px;

}
#output {
    min-width:70%;
   max-width: fit-content ;   
    min-height:90px;
    border: 1px solid black;
}
</style>