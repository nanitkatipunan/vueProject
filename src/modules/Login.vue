<template>
  <div id="background" style="padding-top:20px;">
    <center>
      <div id="divLogin" class="col-sm-3 my-sm-5 border rounded" style="margin-left:0.5%">
        <form class="container">
          <center>
            <h1 id="login">Login</h1>
          </center>
          <hr>
          <div class="row">
            <label id="username" for="loginUsername">Username:</label>
            <input
              required
              v-model="username"
              name="username"
              class="form-control"
              placeholder="Enter Username"
            > 
            <br>
          </div>
          <br>
          <div class="row">
            <label id="pass" for="loginPassword">Password:</label>
            <input
              required
              v-model="password"
              type="password"
              name="password"
              class="form-control"
              id="loginPassword"
              placeholder="Enter Password"
            >
          </div>
          <br>
          <button id="btnLogin" class="btn btn-primary" @click="login">
            <h6>Login</h6>
          </button>
          <br>
          <br>
        </form>
      </div>
    </center>
  </div>
</template>
<style scoped lang="scss">
@import "assets/colors.scss";


#username {
  color: whitesmoke !important;
}
#pass {
  color: whitesmoke !important;
}
#login{
  color:aliceblue;

}
#divLogin{
  background-color:rgba(0, 0, 0, 0.4)
}
</style>
<script>
import AUTH from 'services/auth'
import jquery from 'jquery'
export default {
  data() {
    AUTH
    return {
      username: "",
      password: ""
    };
  },
  methods: {
    
    submit: function(e) {
      e.preventDefault();
      AUTH.login(this.username, this.password)
    },
    login(){
      jquery.ajax({
        url:'http://localhost:3000/user',
        method:'get',
        headers:{
          'Access-Control-Allow-Origin':'*'
        }
      })
    }

  }
};
</script>
