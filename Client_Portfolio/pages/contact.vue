<template>
  <div class="container-fluid body">
    <ul class="pushFor">
      <li><a href="/">Home</a></li>
      <li style="border-top-right-radius: 30px">
        <a href="/aboutMe">About Me</a>
      </li>
      <li>
        <a href="/contact" class="active">Contact</a>
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
              />
              <label for="lname">Last Name</label>
              <input
                type="text"
                id="lname"
                name="lastname"
                placeholder="Your last name.."
              />
              <label for="country">Country</label>
              <select id="country" name="country">
                <option value="australia">Austria</option>
                <option value="canada">Canada</option>
                <option value="usa">USA</option>
              </select>
              <label for="subject">Subject</label>
              <textarea
                id="subject"
                name="subject"
                placeholder="Write something.."
                style="height: 170px"
              ></textarea>
              <input type="submit" value="Submit" />
            </form>
          </div>
        </div>
      </div>
      <div class="col-lg-3 col-md-3 col-sm-3 col-xs-3"></div>
    </div>
    <br /><br />
    <footer class="container-fluid text-center">
      <div class="row">
        <div class="col-lg-12 col-md-12 col-sm-12 col-xs-12">
          <p>Footer Text</p>
        </div>
      </div>
    </footer>
  </div>
</template>
<script>
export default {};
</script>
<style scoped>
.body {
  margin: 0;
  padding: 0;
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
  text-align: center;
  color: black;
  padding: 14px 16px;
  text-decoration: none;
}

.active {
  background-color: #a47e3c;

  border-bottom-left-radius: 30px;
  border-bottom-right-radius: 0;
  border-top-left-radius: 0;
}

input[type="text"],
select,
textarea {
  width: 100%;
  padding: 12px;
  border: 1px solid #ccc;
  margin-top: 6px;
  margin-bottom: 16px;
  resize: vertical;
}

input[type="submit"] {
  background-color: #4caf50;
  color: white;
  padding: 12px 20px;
  border: none;
  cursor: pointer;
}

input[type="submit"]:hover {
  background-color: #45a049;
}

/* Style the container/contact section */
.backgroundOfContact {
  background-color: #f3e4ca;
  padding: 10px;
  padding-top: 60px;
}

/* Clear floats after the columns */
.row:after {
  content: "";
  display: table;
  clear: both;
}

/* Responsive layout - when the screen is less than 600px wide, make the two columns stack on top of each other instead of next to each other */
@media screen and (max-width: 600px) {
  input[type="submit"] {
    width: 100%;
    margin-top: 0;
  }
}

footer {
  background-color: #a47e3c;
  padding: 25px;
}

.pushBack {
  z-index: 900;
}

.pushFor {
  z-index: 950;
}
</style>
