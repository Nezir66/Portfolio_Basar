<template>
  <div class="body">
    <nuxt-link
      to="/"
      style="float: left; margin: -3%; color: black; transform: scale(3)"
      ><i class="fa fa-home"></i
    ></nuxt-link>
    <div class="calculator" onselectstart="return false">
      <div class="display">{{ display }}</div>
      <div @click="clear" class="button darker">C</div>
      <div @click="history" class="button darker">h</div>
      <div @click="percent" class="button darker">%</div>
      <div @click="divide" class="button operator">÷</div>
      <div @click="append(7)" class="button">7</div>
      <div @click="append(8)" class="button">8</div>
      <div @click="append(9)" class="button">9</div>
      <div @click="multiply" class="button operator">x</div>
      <div @click="append(4)" class="button">4</div>
      <div @click="append(5)" class="button">5</div>
      <div @click="append(6)" class="button">6</div>
      <div @click="subtract" class="button operator">-</div>
      <div @click="append(1)" class="button">1</div>
      <div @click="append(2)" class="button">2</div>
      <div @click="append(3)" class="button">3</div>
      <div @click="add" class="button operator">+</div>
      <div @click="append(0)" class="button button-bottom">0</div>
      <div @click="decimal" class="button darker button-bottom">.</div>
      <div @click="sign" class="button darker">+/-</div>
      <div @click="equal" class="button operator button-bottom">=</div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      previous: null,
      display: "",
      operator: null,
      operatorClicked: false,
      test: [],
      Solution: "",
    };
  },
  methods: {
    clear() {
      this.display = 0;
    },
    sign() {
      this.display =
        this.display < 0
          ? (this.display = this.display - this.display * 2)
          : (this.display = this.display - this.display * 2);
    },
    percent() {
      this.display = this.display / 100;
    },
    append(number) {
      if (this.operatorClicked === true) {
        this.display = "";
        this.operatorClicked = false;
      }
      this.display =
        this.display === 0
          ? (this.display = number)
          : "" + this.display + number;
    },
    decimal() {
      if (this.display.indexOf(".") === -1) {
        this.append(".");
      }
    },
    divide() {
      this.test = [];
      this.operator = (a, b) => a / b;
      this.previous = this.display;
      this.operatorClicked = true;
      this.test.push(this.previous + "/");
    },
    multiply() {
      this.test = [];
      this.operator = (a, b) => a * b;
      this.previous = this.display;
      this.operatorClicked = true;
      this.test.push(this.previous + "x");
    },
    subtract() {
      this.test = [];
      this.operator = (a, b) => a - b;
      this.previous = this.display;
      this.operatorClicked = true;
      this.test.push(this.previous + "-");
    },
    add() {
      this.test = [];
      this.operator = (a, b) => a + b;
      this.previous = this.display;
      this.operatorClicked = true;
      this.test.push(this.previous + "+");
    },
    equal() {
      this.test.push(this.display);
      this.display = this.operator(Number(this.previous), Number(this.display));
      this.Solution = this.display;
      this.previous = null;
      this.operatorClicked = true;
    },
    history() {
      this.display = this.test[0] + this.test[1] + "=" + this.Solution;
    },
  },
};
</script>

<style scoped>
.body {
  font-family: "Franklin Gothic Medium", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #111;
  margin: auto;
  z-index: 1;
  padding: 5%;
}

@media only screen and (min-width: 768px) {
  .body {
    margin: auto;
  }
}
.calculator {
  margin: auto;
  width: 80vw;
  font-size: 2rem;
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  grid-auto-rows: minmax(10vh, auto);
  border: 5px solid #111;
  box-shadow: -3px 3px 15px rgba(17, 17, 17, 0.4);
  line-height: 10vh;
}

.display {
  grid-column: 1 / 5;
  background: linear-gradient(15deg, hsl(0, 1%, 66%) 0%, hsl(0, 0%, 80%) 100%);
  border: 1px solid #111;
  border-top: 0;
  font-size: 2.5rem;
  cursor: default;
  overflow: hidden;
  text-overflow: ellipsis;
  padding: 0 1rem;
}

.button {
  background: linear-gradient(15deg, hsl(0, 1%, 51%) 0%, hsl(0, 0%, 80%) 100%);
  border: 1px solid #111;
  cursor: pointer;
}

.button:active {
  outline: none;
  border: 1px solid #000000bf;
  box-shadow: inset 0px 0px 5px #00000080;
  -moz-box-shadow: inset 0px 0px 5px #00000080;
  -webkit-box-shadow: inset 0px 0px 5px #00000080;
}

.button-bottom {
  border-bottom: 0;
}

.operator {
  background: hsl(150, 4%, 91%);
  background: linear-gradient(
    15deg,
    hsl(154, 14%, 19%) 0%,
    hsl(153, 48%, 49%) 100%
  );
}

.darker {
  background: hsl(0, 0%, 100%);
  background: linear-gradient(15deg, hsl(0, 1%, 35%) 0%, hsl(0, 0%, 70%) 100%);
}

@media only screen and (min-width: 768px) {
  .calculator {
    width: 50vw;
    grid-auto-rows: minmax(7.5vh, auto);
    line-height: 7.5vh;
  }
}

@media only screen and (min-width: 1024px) {
  .calculator {
    width: 30vw;
  }
}

@media only screen and (min-width: 1280px) {
  .calculator {
    width: 20vw;
  }
}

@media only screen and (min-width: 1600px) {
  .calculator {
    width: 15vw;
  }
}
</style>