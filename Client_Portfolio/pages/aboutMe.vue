<template>
  <div class="body">
    <ul>
      <li style="border-top-right-radius: 30px"><a href="/">Home</a></li>
      <li><a href="/news" class="active">About Me</a></li>
      <li
        style="
          border-bottom-left-radius: 30px;
          border-top-right-radius: 30px;
          border-bottom-right-radius: 0;
        "
      >
        <a href="/contact">Contact</a>
      </li>
      <li>
        <a href="/aboutMe" class="active" style="border-top-right-radius: 0"
          >&nbsp;</a
        >
      </li>
    </ul>
    <br /><br />
    <footer class="container-fluid text-center">
      <p>Footer Text</p>
    </footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      space: "",
    };
  },
};
</script>
<style scoped>
.body {
  margin: 0;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
}
footer {
  background-color: #a47e3c;
  padding: 25px;
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
  border-radius: 30px;
  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 0;
  border-top-left-radius: 0;
}
</style>
