<template>
  <div id="app">

    <h1>Vue Flex</h1>

    <flex-container 
      direction="row"
      alignItems="center"
      justifyContent="space-between"
      padding="10px"
      margin="10px 0 0 0"
      style="background: #d2d2d2" 
    >
      <flex-item style="background: #eaeaea;" grow="1" padding="10px">FLEX</flex-item>
    </flex-container>

    <flex-container 
      direction="row"
      alignItems="center"
      justifyContent="space-between"
      padding="10px"
      margin="10px 0 0 0"
      style="background: #d2d2d2" 
    >
      <flex-item style="background: #eaeaea;" grow="1" margin="0 5px 0 0" padding="10px">FLEX 1</flex-item>
      <flex-item style="background: #eaeaea;" grow="1" margin="0 5px 0 0" padding="10px">FLEX 2</flex-item>
      <flex-item style="background: #eaeaea;" grow="1" margin="0 5px 0 0" padding="10px">FLEX 3</flex-item>
      <flex-item style="background: #eaeaea;" grow="1" padding="10px">FLEX 4</flex-item>
    </flex-container>

    <flex-container 
      direction="column"
      padding="10px"
      margin="10px 0 0 0"
      style="background: #d2d2d2" 
    >
      <flex-item style="background: #eaeaea;" margin="0 0 5px 0" padding="10px">FLEX 1</flex-item>
      <flex-item style="background: #eaeaea;" margin="0 0 5px 0" padding="10px">FLEX 2</flex-item>
      <flex-item style="background: #eaeaea;" margin="0 0 5px 0" padding="10px">FLEX 3</flex-item>
      <flex-item style="background: #eaeaea;" padding="10px">FLEX 4</flex-item>
    </flex-container>
  </div>
</template>

<script>
import {FlexContainer, FlexItem} from '../lib.js'

export default {
  name: 'app',
  components: {
    FlexContainer,
    FlexItem
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
