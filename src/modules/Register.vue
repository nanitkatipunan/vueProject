<template>
  <center>
    <div id="divFrom" class="col-sm-3 my-sm-5 border rounded" style="margin-left:0.5%">
      <form class="container">
        <center>
          <h1 id="register">Register</h1>
        </center>
        <hr>
        <div>
          <div class="row">
            <label for="inputfname">Username:</label>
            <input
              v-model="content.username"
              class="form-control"
              name="username"
              placeholder="Enter Username"
            >
          </div>
          <br>
          <div class="row">
            <br>
            <label for="inputEmail">Email:</label>
            <input type="email" class="form-control" v-model="content.email" placeholder="Enter Email">
          </div>
          <br>
          <div class="row">
            <label for="inputPassword">Password:</label>
            <input
              type="password"
              v-model="content.password"
              class="form-control"
              name="password"
              id="inputPassword4"
              placeholder="Password"
            >
            <span></span>
            <br>
            <br>
          </div>
          <div class="row">
            <label for="inputConPassword">Confirm Password:</label>
            <input
              type="password"
              class="form-control"
              id="inputConPassword"
              placeholder="Confirm Password"
            >
            <span></span>
            <br>
            <br>
          </div>
        </div>
        <br>
        <button
          id="btnSubmit"
          type="submit"
          class="btn btn-primary"
          @click="submit"
        >
          <h6>Register</h6>
        </button>
        <br>
        <p id="already">Already have an account?</p>
        <router-link to="/Login">Login</router-link>
        <br>
        <br>
      </form>
    </div>
  </center>
</template>
<style scoped lang="scss">
// @import"assets/colors.scss";
// #username{
//   color: $primary !important;
// }
// #pass{
//   color: $primary !important;
#register{
  color: whitesmoke;
}
label{
  color:whitesmoke;
}
#already{
  color: whitesmoke;
}
#divFrom{
  background-color:rgba(0, 0, 0, 0.4)
}
</style>
<script>
// import ROUTER from "router";
import AUTH from "services/auth";
export default {
  data() {
    return {
      auth: AUTH,
      content: {
        username: "",
        email: "",
        password: "",
        conpassword: ""
      }
    };
  },
  methods: {
    submit: function(e) {
      e.preventDefault();
      sessionStorage.setItem("Username", this.content.username),
        sessionStorage.setItem("Email", this.content.email),
        sessionStorage.setItem("Password", this.content.password),
        AUTH.register(this.content.username, this.content.password);
    }
  }
};
</script>