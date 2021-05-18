<template>
    <div class="body">
    <ul>
      <li style="border-top-right-radius: 30px"><nuxt-link to="/">Home</nuxt-link></li>
      <li><nuxt-link to="/news" class="active">About Me</nuxt-link></li>
      <li
        style="
          border-bottom-left-radius: 30px;
          border-top-right-radius: 30px;
          border-bottom-right-radius: 0;
        "
      >
        <nuxt-link to="/contact">Contact</nuxt-link>
      </li>
      <li>
        <a href="/aboutMe" class="active" style="border-top-right-radius: 0"
          >&nbsp;</a
        >
      </li>
    </ul>
    </div>
</template>
<style scoped>
.body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
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
  color: #a47e3c;
  text-align: center;
  padding: 14px 16px;
  text-decoration: none;
}

.active {
  background-color: #a47e3c;
  color: #f3e4ca;
  border-radius: 30px;
  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 0;
  border-top-left-radius: 0;
}
</style>