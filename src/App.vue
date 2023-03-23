<template>
  <HelloWorld/>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  }
}
</script>

<style>
@import url('assets/plugins/bootstrap/css/bootstrap.min.css');

@font-face {
  font-family: nunito;
  src: url('assets/fonts/nunito-sans/Nunito-Regular.ttf') ;
  font-weight: regular;
}
@font-face {
  font-family: nunito;
  src: url('assets/fonts/nunito-sans/Nunito-ExtraLight.ttf') ;
  font-weight: 100;
}
@font-face {
  font-family: nunito;
  src: url('assets/fonts/nunito-sans/Nunito-Light.ttf') ;
  font-weight: 300;
}
@font-face {
  font-family: nunito;
  src: url('assets/fonts/nunito-sans/Nunito-Medium.ttf') ;
  font-weight: 500;
}
@font-face {
  font-family: nunito;
  src: url('assets/fonts/nunito-sans/Nunito-Bold.ttf') ;
  font-weight: 600;
}
@font-face {
  font-family: nunito;
  src: url('assets/fonts/nunito-sans/Nunito-ExtraBold.ttf') ;
  font-weight: 800;
}
html {
  height: 100%;
}
body {
  font-family: nunito;
    overflow-x: hidden;
    box-sizing: border-box;
    height: 100%;
    margin: 0;
    padding: 0;
    display: flex;
    align-items: center;
    justify-content: center;
}
</style>
