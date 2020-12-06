<template>
  <div class="body">
    <div class="hero-image">
      <div class="hero-text">
        <h1 style="font-size:50px;">Nezir Basar</h1>
        <h3>Welcome to my Portfolio</h3>
      </div>
    </div>
    <ul class="pushFor">
      <li><a class="active" href="/">Home</a></li>
      <li style="border-radius:0;border-bottom-left-radius: 30px;"><a href="/aboutMe">About Me</a></li>
      <li style="border-top-right-radius: 30px;border-bottom-right-radius: 0;"><a href="/contact">Contact</a></li>
      <li>
        <a href="#" class="active" style="border-top-right-radius:0;border-bottom-left-radius:30px;">&nbsp;</a>
      </li>
    </ul>
    <br>
    <div class="container-fluid bg-3 text-center pushBack">
      <h2>Some of my Work</h2>
      <br>
      <div class="row">
        <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
        <div class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
          <h3></h3>
          <transition>
            <img
            src="~/assets/Plakat-1.png"
            class="img-responsive"
            style="width:100%"
            alt="Image"
            v-if="openDiplo"
            >          
          </transition>
          <br>
          <button @click="showDiplo">Diploma project at the TGM</button>
          <hr>
          <button @click="showCalc">Calculator programmed with Vue.js</button>
          <hr>
          <transition name="calculator">
            <img
            src="~/assets/Robotic_vacuum_cleaner.png"
            class="img-responsive"
            style="width:50%;margin:auto;"
            alt="Image"
            v-if="openRobot"
            >         
          </transition>
          <br>
          <button @click="showRobot">Robotic vacuum cleaner ROS Program</button>
          <hr>
          <transition-group name="calculator">
            <img
            src="~/assets/monsterVsHero.png"
            class="img-responsive"
            style="width:100%;margin:auto;cursor:pointer;"
            alt="Image of Hero vs Monster Game"
            v-if="openGameHero"
            @click="goToHeroGame"
            :key="1"
            >
            <a href="https://github.com/Nezir66/Monster_vs_Hero.git" v-if="openGameHero" :key="1"><i class="fa fa-github" style="transform: scale(2);"></i></a>  
          </transition-group>
          <br><br>
          <button @click="showGameHero">Monster vs Hero Program</button>
          <br>
        </div>
        <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
      </div>
    </div>
    <br><br>
    <footer class="container-fluid text-center">
      <p>Footer Text</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      openDiplo: false,
      openRobot: false,
      openGameHero: false,
    }
  },
  methods: {
    showDiplo(){
      this.openDiplo = !this.openDiplo;
    },
    showCalc(){
      this.$router.push('/demoProject/calculator')
    },
    showRobot(){
      this.openRobot = !this.openRobot;
    },
    showGameHero(){
      this.openGameHero = !this.openGameHero;
    },
    goToHeroGame(){
      this.$router.push('/demoProject/monsterVsHero')
    }
  }
}
</script>

<style scoped>
.navbar {
  margin-bottom: 0;
  border-radius: 0;
}

footer {
  background-color:#A47E3C;
  padding: 25px;
}

.body {
  background-color: white;
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
}

.hero-image {
  background-image: url("https://images.unsplash.com/photo-1507372953381-f69d9aeac620?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1350&q=80");
  background-color: #cccccc;
  height: 500px;
  background-position: center;
  background-repeat: no-repeat;
  background-size: cover;
  position: relative;
}

.hero-text {
  text-align: center;
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
  color: black;
  text-shadow: 2px 2px 5px white;
}
ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
  overflow: hidden;
  background-color: #A47E3C;
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
}

li {
  float: left;
  background-color: #F3E4CA;
}

li a {
  display: block;
  color: black;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.active {
  background-color: #A47E3C;
  border-radius: 0;
  border-top-right-radius: 30px;
}

.pushBack{
  z-index: 900;
}

.pushFor{
  z-index: 950;
}
</style>
