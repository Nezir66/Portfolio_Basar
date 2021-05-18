<template>
  <div class="container-fluid body">
    <ul class="pushFor">
      <li><nuxt-link to="/">Home</nuxt-link></li>
      <li style="border-top-right-radius: 30px">
        <nuxt-link to="/aboutMe">About Me</nuxt-link>
      </li>
      <li>
        <nuxt-link to="/contact" class="active">Contact</nuxt-link>
      </li>
    </ul>
    <div class="row" style="height: 50px"></div>
    <div class="container-fluid pushBack">
      <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
      <div class="col-lg-6 col-md-6 col-sm-6 col-xs-6 backgroundOfContact">
        <div style="text-align: center">
          <h2>Contact Me</h2>
          <p>Please leave me a message</p>
        </div>
        <hr>
        <div class="row pushBack">
          <div class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <img
              src="https://images.unsplash.com/photo-1516387938699-a93567ec168e?ixid=MXwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHw%3D&ixlib=rb-1.2.1&auto=format&fit=crop&w=1351&q=80"
              style="width: 100%"
            />
          </div>
          <div class="col-lg-6 col-md-6 col-sm-6 col-xs-6">
            <form action="/action_page.php">
              <label for="fname">First Name</label>
              <input
                type="text"
                id="fname"
                name="firstname"
                placeholder="Your name.."
                v-model="firstName"
              />
              <label for="lname">Last Name</label>
              <input
                type="text"
                id="lname"
                name="lastname"
                placeholder="Your last name.."
                v-model="lastName"
              />
              <label for="country">Country</label>
              <input
                type="text"
                id="country"
                name="country"
                placeholder="Country.."
                v-model="country"
              />
              <label for="subject">Subject</label>
              <textarea
                id="subject"
                name="subject"
                placeholder="Write something.."
                style="height: 170px"
                v-model="subject"
              ></textarea>
              <a class="mailtoui" type="submit" value="Submit" :href="'mailto:nezirbasar@outlook.com?subject=Message%20from%20'+firstName+'%20'+lastName+'%20(Country:%20'+country+')'+'&body='+subject">Submit</a>
            </form>
          </div>
        </div>
      </div>
      <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
    </div>
      <footer>
        <br><br>
      </footer>
  </div>
</template>
<script>
export default {
  data() {
    return {
      firstName: "",
      lastName: "",
      country: "",
      subject: "",
    }
  },
};
</script>
<style scoped>
.body {
  margin: 0;
  padding: 0;
  font-family: Arial, Helvetica, sans-serif;
  font-size: 20px;
  overflow: hidden;
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
  text-align: center;
  color: #a47e3c;
  padding: 14px 16px;
  text-decoration: none;
}

.active {
  background-color: #a47e3c;
  color: #f3e4ca;
  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 0;
  border-top-left-radius: 0;
}

a[type="text"],
input,
select,
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
  color: #a47e3c;
  background-color: #f3e4ca;
}

a[type="submit"] {
  background-color: #f3e4ca;
  color: #a47e3c;
  padding: 12px 20px;
  border: none;
  cursor: pointer;
}

a[type="submit"]:hover {
  background-color: grey;
  color: #f3e4ca;
  text-decoration: none;
}

/* Style the container/contact section */
.backgroundOfContact {
  background-color:#a47e3c;
  color: #f3e4ca;
  box-shadow: 0 0 15px rgba(0, 0, 0, 0.5);
  padding: 10px;
  padding-top: 60px;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

.pushBack {
  margin-bottom: 121.5px;
}

/* Responsive layout - when the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  a[type="submit"] {
    width: 100%;
    margin-top: 0;
  }
}

.pushBack {
  z-index: 900;
}

.pushFor {
  z-index: 950;
}
</style>
