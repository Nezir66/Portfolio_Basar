<template>
  <div>
    <navbar></navbar>

    <carousel-3d style="margin-top:200px;margin-bottom:676px;" :controls-visible="true" :clickable="false">
      <slide
        class="main"
        v-for="(data, index) in data"
        :key="data._id"
        :index="index"
      >
        <section v-for="(info, index2) in data" v-bind:key="index2" class="timeline">
          <div>
          <h2 v-if="info.status">{{info.status}}</h2>
          <ul  v-else>
            <li>
              <span></span>
              <div>{{ info.school }}</div>
              <div>{{ info.address }}</div>
              <div>{{ info.course }}</div>
              <div class="year">
                <span>{{ info.yearEnd }}</span>
                <span>{{ info.yearStart }}</span>
              </div>
            </li>
          </ul>
          </div>
        </section>
      </slide>
      <slide class="main" :key="1" :index="2">
            <h2 style="margin-left: 45px;">Skills</h2>
        <ul>
          <li v-for="(skill, index3) in skills" v-bind:key="index3">
        <div class="skill" >
          <p>{{ skill.skill }}</p>
              <p style="font-size: 10pt;">{{ skill.info }}</p>
        </div>
          </li>
        </ul>
        
      </slide>
      <slide class="main" :key="1" :index="3">
        <h2 style="margin-left: 45px; margin-bottom: 30px;">Media</h2>
        <a href="https://www.linkedin.com/in/nezir-basar-314bb51ba/" class="media linkedin">Linkedin</a>
        <a href="https://www.instagram.com/nezirbasar/" class="media instagram">Instagram</a>
        <a href="https://www.xing.com/profile/Nezir_Basar4/cv" class="media xing">Xing</a>
        <a href="https://github.com/Nezir66/" class="media github">Github</a>
      </slide>
    </carousel-3d>
          <footer>
        <br><br>
      </footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      space: "",
      skills: [
        {
          skill: "Web Development",
          info: "HTML | CSS | JavaScript"
        },
        {
          skill: "Java",
          info: "Spring",
        },
        {
          skill: "Python",
          info:"AI"
        },
        {
          skill: "Linux",
          info:"Bash | Architecture"
        },
        {
          skill: "Databases",
          info: "Oracle | MySQL | PostgreSQL | MongoDB"
        },
        {
          skill:"Languages",
          info:"German | English | Turkish"
        },
      ],
      data: [
        [
          {status:  "Education"},
        {
          school: "FH - Technikum Vienna ",
          address: "BSc | Smart Homes and Assistive Technologies",
          course: "Specialization: Web Development ",
          yearStart: "2019",
          yearEnd: "2021"
        },
        {
          school: "Technologisches Gewerbemuseum ",
          address: "Matura | Electrical engineering",
          course: "Specialization: Automation technology ",
          yearStart: "2014",
          yearEnd: "2019"
        }
      ],
      [
        { status:     "Work Experience"},
        {
          school: "BAWAG Group",
          address: "Internship | Full Stack Developer",
          yearStart: "2021",
          yearEnd: "till today"
        },
        {
          school: "Expert Babinsky",
          address: "Internship | Electrician",
          yearStart: "2017",
          yearEnd: "2017"
        }
      ]
      ]
    };
  },
  methods: {}
};
</script>
<style lang="scss" scoped>
.skill {
  width: 400px;
  padding: 5px;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.5);
  height: 50px;
  margin: auto;
  margin-top: 15px;

}
footer {
  background-color: #a47e3c;
  padding: 25px;
}
.media {
      height: 40%;
    width: 49%;
    display: inline-block;
    text-align: center;
  box-shadow: 0 1px 4px rgba(0, 0, 0, 0.5);
      padding: 70px;
      font-size: 15pt;
}

.media.xing:hover {
  text-decoration: none;
  color: #cfdc00 ;
  background-color: #026466;
}
.media.instagram:hover {
  text-decoration: none;
  color: white;
  background-image: linear-gradient(180deg,rgb(81, 91, 212), rgb(129, 52, 175), rgb(221, 42, 123),rgb(245, 133, 41),rgb(254, 218, 119));
}
.media.linkedin:hover {
  text-decoration: none;
  background-color: #2867B2;
  color: white;
}
.media.github:hover {
  text-decoration: none;
  background-color: #333;
  color: white;
}

footer {
  background-color: #a47e3c;
  padding: 25px;
}
@import url("https://fonts.googleapis.com/css?family=Montserrat");
$font-stack: "Montserrat", sans-serif;
$font-color: #fff;
$bg-color: #fff;
$dark-blue: #a47e3c;
$light-blue: brown;

@mixin clearfix {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
}
@mixin set-border($thickness, $color, $radius) {
  border: $thickness solid $color;
  border-radius: $radius;
}

body {
  background-color: $bg-color;
}
*,
*::before,
*::after {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: $font-stack;
  color: $font-color;
}
.carousel-3d-container{
  overflow: unset;
}
.main {
  width: 32em!important;
  height: 500px!important;
  margin: 1em auto;
  margin-left: 20px;
  padding: 40px;
  background: $dark-blue;
  border-radius: 4px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.5);
}
.block {
  display: inline-block;
}
.timeline {
  padding: 5px 45px;
  ul {
    position: relative;
    &::before {
      @include clearfix();
      height: 100%;
    }
  }
  li {
    position: relative;
    margin: 60px 35px;
    width: 100%;
    list-style: none;
    line-height: 25px;
    & > span {
      @include clearfix();
      left: -25px;
      height: 110%;
      @include set-border(2px, $font-color, none);
    }
    & > span::before,
    & > span::after {
      @include clearfix();
      width: 14px;
      height: 14px;
      @include set-border(3px, $font-color, 50%);
      left: -7px;
      background: $light-blue;
    }
    & > span::before {
      top: -15px;
    }
    & > span::after {
      top: 100%;
    }
    div {
      &:nth-child(2) {
        font-size: 1.2em;
      }
      &:nth-child(3),
      &:nth-child(4) {
        font-size: 1em;
        font-style: italic;
        color: white;
      }
    }
    .year span {
      position: absolute;
      font-size: 1em;
      left: -85px;
      width: 40px;
      text-align: right;
      &:first-child {
        top: -20px;
      }
      &:last-child {
        top: 100%;
      }
    }
  }
}
</style>
