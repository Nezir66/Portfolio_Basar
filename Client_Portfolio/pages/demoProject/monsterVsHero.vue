<template>
  <div style="text-align: center; padding: 5%">
    <a
      href="/"
      style="float: left; margin: -3%; color: black; transform: scale(3)"
      ><i class="fa fa-home"></i
    ></a>
    <transition-group name="slide" mode="in-out">
      <section class="row" key="player">
        <div class="small-6 columns">
          <h1 class="text-center">YOU</h1>
          <div class="healthbar">
            <div
              class="healthbar text-center"
              style="background-color: green; margin: 0; color: white"
              :style="{ width: playerHealth + '%' }"
            >
              {{ playerHealth }}
            </div>
          </div>
        </div>
        <div class="small-6 columns">
          <h1 class="text-center">MONSTER</h1>
          <div class="healthbar">
            <div
              class="healthbar text-center"
              style="background-color: green; margin: 0; color: white"
              :style="{ width: monsterHealth + '%' }"
            >
              {{ monsterHealth }}
            </div>
          </div>
        </div>
      </section>
      <section class="row controls" v-if="!startGame" key="start">
        <div class="small-12 columns">
          <button id="start-game" class="button" @click="runningGame">
            START NEW GAME
          </button>
        </div>
      </section>

      <section class="row controls" v-else key="panels">
        <div class="small-12 columns">
          <button id="attack" class="button" @click="attack">ATTACK</button>
          <button id="special-attack" class="button" @click="specialAttack">
            SPECIAL ATTACK
          </button>
          <button id="heal" class="button" @click="heal">HEAL</button>
          <button id="give-up" class="button" @click="giveUp">GIVE UP</button>
        </div>
      </section>
    </transition-group>
    <transition-group name="slide" mode="out-in">
      <section class="row log" v-if="turns.length > 0" key="hero">
        <div class="small-12 columns">
          <ul>
            <transition-group name="fade" mode="in-out">
              <li
                v-for="turn in turns"
                :class="{
                  'player-turn': turn.isHero,
                  'monster-turn': turn.isMonster,
                }"
                :key="turn"
              >
                {{ turn.damage }}
              </li>
            </transition-group>
          </ul>
        </div>
      </section>
    </transition-group>
  </div>
</template>

<script>
export default {
  head() {
    return {
      link: [
        { rel: "stylesheet", href: "/css/app.css" },
        { rel: "stylesheet", href: "/css/foundation.min.css" },
      ],
    };
  },
  data() {
    return {
      playerHealth: 100,
      monsterHealth: 100,
      startGame: false,
      turns: [],
    };
  },
  methods: {
    runningGame: function () {
      this.startGame = true;
      this.playerHealth = 100;
      this.monsterHealth = 100;
      this.turns = [];
    },
    attack: function () {
      let damage = this.countdamage(15, 5);
      this.playerHealth -= damage;
      this.turns.unshift({
        isMonster: true,
        damage: "The Monster hits" + damage + "damage",
      });
      damage = this.countdamage(10, 3);
      this.monsterHealth -= damage;
      this.turns.unshift({
        isHero: true,
        damage: "The Hero hits" + damage + "damage",
      });
      this.whoWon();
    },
    specialAttack: function () {
      let damage = this.countdamage(15, 5);
      this.playerHealth -= damage;
      this.turns.unshift({
        isMonster: true,
        damage: "The Monster hits" + damage + "damage",
      });

      damage = this.countdamage(30, 15);
      this.monsterHealth -= damage;
      this.turns.unshift({
        isHero: true,
        damage: "The Hero hits" + damage + "damage",
      });
      this.whoWon();
    },
    heal: function () {
      if (this.playerHealth <= 90) {
        let healPlayer = this.countdamage(20, 10);
        this.playerHealth += healPlayer;
        this.turns.unshift({
          isHero: true,
          damage: "The Hero healed" + healPlayer + "damage",
        });
      } else {
        this.playerHealth = 100;
        this.turns.unshift({
          isHero: true,
          damage: "The Hero healed completly",
        });
      }

      let damage = this.countdamage(15, 5);
      this.playerHealth -= damage;
      this.turns.unshift({
        isMonster: true,
        damage: "The Monster hits" + damage + "damage",
      });
    },
    giveUp: function () {
      this.stopGame();
    },
    countdamage: function (max, min) {
      return Math.max(Math.floor(Math.random() * max) + 1, min);
    },
    whoWon: function () {
      if (this.playerHealth <= 0) {
        alert("You Lost!");
        this.startGame = false;
        return;
      } else if (this.monsterHealth <= 0) {
        alert("You won!");
        this.startGame = false;
      }
    },
    stopGame: function () {
      this.startGame = false;
    },
  },
};
</script>
