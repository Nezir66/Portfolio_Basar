<template>
  <div>
    <Background />
    <Nuxt />
  </div>
</template>

<script>
import Background from "../components/background.vue";
export default {
  components: {
    Background,
  },
};
</script>

<style>
.v-enter {
  opacity: 0;
  width: 0;
  margin: auto;
}

.v-enter-active {
  animation: fade-in-diplo ease-in-out 2s;
}

.v-leave {
  opacity: 1;
  width: 100%;
  margin: auto;
}

.v-leave-active {
  animation: fade-out-diplo ease-in-out 2s;
}

.calculator-enter {
  opacity: 0;
  width: 0;
  margin: auto;
}

.calculator-enter-active {
  animation: fade-in-calc ease-in-out 2s;
}

.calculator-leave {
  opacity: 1;
  width: 35%;
  margin: auto;
}

.calculator-leave-active {
  animation: fade-out-calc ease-in-out 2s;
}

.game-enter {
  opacity: 0;
  width: 0;
  margin: auto;
}

.game-enter-active {
  animation: fade-in-game ease-in-out 2s;
}

.game-leave {
  opacity: 1;
  width: 100%;
  margin: auto;
}

.game-leave-active {
  animation: fade-out-game ease-in-out 2s;
}
.robot-enter {
  opacity: 0;
  width: 0;
  margin: auto;
}

.robot-enter-active {
  animation: fade-in-robot ease-in-out 2s;
}

.robot-leave {
  opacity: 1;
  width: 50%;
  margin: auto;
}

.robot-leave-active {
  animation: fade-out-robot ease-in-out 2s;
}

@keyframes fade-in-diplo {
  0% {
    opacity: 0;
    width: 0;
    margin: auto;
  }
  100% {
    opacity: 1;
    width: 100%;
    margin: auto;
  }
}

@keyframes fade-out-diplo {
  0% {
    opacity: 1;
    width: 100%;
    margin: auto;
  }
  100% {
    opacity: 0;
    width: 0;
    margin: auto;
  }
}

@keyframes fade-in-robot {
  0% {
    opacity: 0;
    width: 0;
    margin: auto;
    margin-bottom: 30px;
  }
  100% {
    opacity: 1;
    width: 50%;
    margin: auto;
    margin-bottom: 30px;
  }
}

@keyframes fade-out-robot {
  0% {
    opacity: 1;
    width: 50%;
    margin: auto;
    margin-bottom: 30px;
  }
  100% {
    opacity: 0;
    width: 0;
    margin: auto;
    margin-bottom: 30px;
  }
}

@keyframes fade-in-game {
  0% {
    opacity: 0;
    width: 0;
    margin: auto;
  }
  100% {
    opacity: 1;
    width: 100%;
    margin: auto;
  }
}

@keyframes fade-out-game {
  0% {
    opacity: 1;
    width: 100%;
    margin: auto;
  }
  100% {
    opacity: 0;
    width: 0;
    margin: auto;
  }
}

@keyframes fade-in-calc {
  0% {
    opacity: 0;
    width: 0;
    margin: auto;
  }
  100% {
    opacity: 1;
    width: 35%;
    margin: auto;
  }
}

@keyframes fade-out-calc {
  0% {
    opacity: 1;
    width: 35%;
    margin: auto;
  }
  100% {
    opacity: 0;
    width: 0;
    margin: auto;
  }
}
</style>
