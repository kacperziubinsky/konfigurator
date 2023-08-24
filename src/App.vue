<template>
  <TheHeader></TheHeader>
  <TheConfig></TheConfig>
</template>

<script>
import TheHeader from './components/TheHeader.vue';
import TheConfig from './components/TheConfig.vue';

export default {
  components:{
    TheHeader,
    TheConfig
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Nunito');
*{
  margin: 0;
  box-sizing: border-box;
}
body{
  font-family: 'Nunito', sans-serif;
  background-color: rgb(173, 173, 173);
}

</style>