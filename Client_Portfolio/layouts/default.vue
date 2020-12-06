<template>
  <div>
    <Background />
    <Nuxt />
  </div>
</template>

<script>
import Background from '../components/background.vue'
export default {
  components: {
    Background
  }
}

</script>

<style>
.v-enter{
  opacity:0; 
  width:0;
  margin:auto;
}

.v-enter-active{
  animation: fade-in-diplo ease-in-out 5s ;
}

.v-leave{
  opacity:1; 
  width:100%;
  margin:auto;
}

.v-leave-active{
  animation: fade-out-diplo ease-in-out 5s ;
}

@keyframes fade-in-diplo {
0% {opacity:0; width:0;margin:auto;}
100% {opacity:1;width:100%;margin:auto;}
}

@keyframes fade-out-diplo {
0% {opacity:1; width:100%;margin:auto;}
100% {opacity:0;width:0;margin:auto;}
}

.calculator-enter{
  opacity:0; 
  width:0;
  margin:auto;
}

.calculator-enter-active{
  animation: fade-in-calc ease-in-out 2s ;
}

.calculator-leave{
  opacity:1; 
  width:100%;
  margin:auto;
}

.calculator-leave-active{
  animation: fade-out-calc ease-in-out 3s ;
}

@keyframes fade-in-calc {
0% {
  opacity:0; 
  width:0;
  margin:auto;
  }
100% {
  opacity:1;
  width:100%;
  margin:auto;
  }
}

@keyframes fade-out-calc {
0% {
  opacity:1; 
  width:100%;
  margin:auto;
  }
100% {
  opacity:0;
  width:0;
  margin:auto;
  }
}

</style>
