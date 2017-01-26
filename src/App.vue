<template>
  <div id="app" style="width: 800px; padding-left: 400px">
    <md-card md-with-hover>
      <md-card-media md-ratio="16:9">
     <img src="./assets/dev-id-logo.jpg" alt="dev-id-logo">
   </md-card-media>
      <md-card-header>
        <div class="md-title">Dev-ID</div>
        <div class="md-subhead">Pawa 3.0</div>
      </md-card-header>

      <md-card-content>
        <form novalidate @submit.stop.prevent="submit">
          <md-input-container>
              <md-input placeholder="Login" v-model="login"></md-input>
            </md-input-container>
  <md-input-container md-has-password>
    <label>Password</label>
    <md-input type="password" v-model="password"></md-input>
  </md-input-container>
  <md-checkbox id="remember" name="remember" v-model="checkbox">Remember me</md-checkbox>
  <md-button class="md-raised md-primary" v-on:click="getCredentials()">Sign in</md-button>
  <md-button class="md-raised" v-on:click="clearFields()">Clear</md-button>


</form>

        <br />
      </md-card-content>
    </md-card>
  </div>
</template>

<script>
export default {
    name: 'app',
    data: function () {
      return {
        password:"",
        login:"",
        checkbox:false
      }
    },
    methods: {
      clearFields: function() {
        this.login="";
        this.password="";
        this.checkbox=false;
      },
      getCredentials:function(){
        console.log("credentials :"+this.login+" "+this.password+" "+this.checkbox);
      }
    }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
