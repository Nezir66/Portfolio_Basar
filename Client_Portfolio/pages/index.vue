<template>
  <div class="body">
    <div class="hero-image">
      <div class="hero-text">
        <h1 style="font-size: 50px">Nezir Basar</h1>
        <h3>Welcome to my Portfolio</h3>
      </div>
    </div>
    <ul class="pushFor">
      <li><a class="active" href="/">Home</a></li>
      <li style="border-radius: 0; border-bottom-left-radius: 30px">
        <a href="/aboutMe">About Me</a>
      </li>
      <li style="border-top-right-radius: 30px; border-bottom-right-radius: 0">
        <a href="/contact">Contact</a>
      </li>
      <li>
        <a
          href="#"
          class="active"
          style="border-top-right-radius: 0; border-bottom-left-radius: 30px"
          >&nbsp;</a
        >
      </li>
    </ul>
    <br />
    <div class="container-fluid bg-3 text-center pushBack">
      <h2>Some of my Work</h2>
      <br />
      <div class="row">
        <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
        <div class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
          <div class="col-xl-12 col-lg-12 col-md-12 col-sm-12">
            <div
              class="row no-gutters border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative"
              style="max-width: 250"
            >
              <div class="sidenav">
                <img src="~/assets/Vue_Calculator.png" />
              </div>
              <div class="content col p-4 d-flex flex-column position-static">
                <h2>Calculator</h2>
                <p>
                  This is a calculator programmed with Vue.js. It can solve
                  basic math calculations and can also show the history.
                </p>
                <a href="https://github.com/Nezir66/Assignment-4-Calculator.git"
                  ><i
                    class="fa fa-github"
                    style="
                      transform: scale(2);
                      color: #a47e3c;
                      margin-left: 2%;
                      position: relative;
                    "
                  ></i
                ></a>
                <a class="demo" @click="goToCalc">Demo</a>
              </div>
            </div>
            <hr />
          </div>
          <br />
          <div class="col-xl-12 col-lg-12 col-md-12 col-sm-12">
            <div
              class="row no-gutters border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative"
            >
              <div class="content col p-4 d-flex flex-column position-static">
                <h2>Monster vs Hero</h2>
                <p>
                  A game where the user is in the role of the hero and tries to
                  kill the monster. The hero has a bunch of skills like attack,
                  special attack or healing.
                </p>
                <a href="https://github.com/Nezir66/Monster_vs_Hero.git"
                  ><i
                    class="fa fa-github"
                    style="
                      transform: scale(2);
                      color: #a47e3c;
                      margin-left: 2%;
                      position: relative;
                    "
                  ></i
                ></a>
                <a class="demo" @click="goToHeroGame">Demo</a>
              </div>
              <div class="sidenav">
                <img src="~/assets/monsterVsHero.png" height="277" />
              </div>
            </div>
            <hr />
          </div>
          <br />
          <div class="col-xl-12 col-lg-12 col-md-12 col-sm-12">
            <div
              class="row no-gutters border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative"
            >
              <div class="sidenav">
                <img
                  src="~/assets/Robotic_vacuum_cleaner.png"
                  width="250"
                  height="250"
                />
              </div>
              <div class="content col p-4 d-flex flex-column position-static">
                <h2>Robotic vacuum cleaner</h2>
                <p>
                  A robotic vacuum cleaner programmed with ROS. It can move on
                  its own and recognizes when an obstacle is in the way.
                </p>
                <a href="https://github.com/Nezir66/Robotic-vacuum-cleaner.git"
                  ><i
                    class="fa fa-github"
                    style="
                      transform: scale(2);
                      color: #a47e3c;
                      margin-left: 2%;
                      position: relative;
                    "
                  ></i
                ></a>
              </div>
            </div>
            <hr />
          </div>
          <br />
          <div class="col-xl-12 col-lg-12 col-md-12 col-sm-12">
            <div
              class="row no-gutters border rounded overflow-hidden flex-md-row mb-4 shadow-sm h-md-250 position-relative"
            >
              <div class="content col p-4 d-flex flex-column position-static">
                <h2>Diploma project at the TGM</h2>
                <p>
                  My diploma project made together with two other colleges.
                  Realization of an "ideal" smart home by combining different
                  smart home systems.
                </p>
                <a class="demo" @click="goToDiplo">PDF</a>
              </div>
              <div class="sidenav">
                <img
                  src="~/assets/Schaltschrank.png"
                  width="250"
                  height="250"
                />
              </div>
            </div>
            <hr />
          </div>
        </div>
        <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
      </div>
    </div>
    <br /><br />
    <footer class="container-fluid text-center">
      <p>Footer Text</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {};
  },
  methods: {
    goToCalc() {
      this.$router.push("/demoProject/calculator");
    },
    goToHeroGame() {
      this.$router.push("/demoProject/monsterVsHero");
    },
    goToDiplo() {
      this.$router.push("/demoProject/diplomaProject");
    },
  },
};
</script>

<style scoped>
.navbar {
  margin-bottom: 0;
  border-radius: 0;
}

footer {
  background-color: #a47e3c;
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
  background-color: #a47e3c;
  position: -webkit-sticky; /* Safari */
  position: sticky;
  top: 0;
}

li {
  float: left;
  background-color: #f3e4ca;
}

li a {
  display: block;
  color: black;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.active {
  background-color: #a47e3c;
  border-radius: 0;
  border-top-right-radius: 30px;
}

.pushBack {
  z-index: 900;
}

.pushFor {
  z-index: 950;
}

.demo {
  border-radius: 5px;
  background-color: #a47e3c;
  color: white;
  width: 70px;
  text-align: center;
  cursor: pointer;
  margin-top: 2%;
}

.bodySingleProject {
  border: 2px solid #a47e3c;
  padding: 0;
}

.sidenav {
  height: 250;
  width: 250;
  float: left;
  overflow-x: hidden;
}

.content {
  text-align: left;
  padding-left: 20px;
  margin-top: 0;
}
</style>
