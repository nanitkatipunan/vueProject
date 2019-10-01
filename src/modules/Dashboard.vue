<template>
  <div>
    <div class="jumbotron">
      <h1 >Dashboard</h1>
    </div>
    <div id="card">
      <b-card no-body class="overflow-hidden" style="max-width: 540px;">
        <center>
        <br>
       <b-img :src="require('assets/mine.png')" rounded="circle"  alt="Circle image" id="userIcon"></b-img>

          <b-row no-gutters>
            <b-card-body>
              <h1>Hi! {{username}}</h1>
              <h3>Welcome to infoCatchApp</h3>
            </b-card-body>
          </b-row>
        </center>
      </b-card>
    </div>
  </div>
</template>

<style scoped>
#card {
  margin-top: 30px;
  margin-left: 400px;
}
.jumbotron{
    padding:20px;
    text-align: center;
}
#image {
  width: 250px;
  height: 220px;
   
}
#userIcon{
  height:160px;
  width:150px;

}
</style>

<script>
// import ROUTER from "router";
export default {
  name: "card",
  data() {
    return {
      username: sessionStorage.getItem("Username")
    };
  },
};
</script>