<template>
  <div class="d-flex justify-center pt-14">
    <v-card width="40%">
      <v-alert type='success' v-model="alert">{{ information }}</v-alert>

      <br />
      <v-card-title> <title title="Welcome To My Site EUY"></title></v-card-title>
      <v-card-text>
        <span>Username</span>
        <v-text-field placeholder="Enter your username" v-model="form.username"></v-text-field>
        <span>Password</span>
        <v-text-field placeholder="Enter your password" type="password" v-model="form.password">
          <h1>{{ msg }}</h1>
        </v-text-field>
      </v-card-text>
      <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn class="primary" depressed @click="login"> Login </v-btn>
        <v-spacer></v-spacer>
      </v-card-actions>
    </v-card>
  </div>
</template>

<script>
export default {
  data() {
    return {
      information: "",
      msg: "",
      alert: false,
      form: {
        username: "",
        password: "",
      },
    };
  },

  methods: {
    login() {
      if (this.form.username == "imam" && this.form.password == "admin") {
        this.alert = true;
        this.information = "SUCCESS";
      } else {
        this.alert = true;
        this.information = "FAILED";
        throw new Error("LOGIN FAILED GUYS");
      }
    },
  },
};
</script>
