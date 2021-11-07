<template>
  <div>
    <MyInput />
    <MyInput error/>
    <MyInput disabled/>
    <MyInput helpText="some interesting text"/>
    <MyInput helpText="some interesting text" error/>
    <MyInput startIcon />
    <MyInput endIcon />
  </div>
</template>

<script>
import MyInput from './components/MyInput.vue'

export default {
  name: 'App',
  components: {
    MyInput
  }
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
</style>
