<template>
  <div class="about">
    <h1>This is an login page</h1>
    <div class="container">
      <div class="row">
        <div class="col-sm"></div>
        <div class="col-sm">
          <form>
            <div class="form-group">
              <label for="exampleInputEmail1">Email address</label>
              <input
                type="email"
                v-model="Email"
                class="form-control"
                id="exampleInputEmail1"
                aria-describedby="emailHelp"
                placeholder="Enter email"
              />
              <small id="emailHelp" class="form-text text-muted"
                >We'll never share your email with anyone else.</small
              >
            </div>
            <div class="form-group">
              <label for="exampleInputPassword1">Password</label>
              <input
                type="password"
                v-model="password"
                class="form-control"
                id="exampleInputPassword1"
                placeholder="Password"
              />
            </div>
            <button type="button" @click="login" class="btn btn-primary">
              Submit
            </button>
          </form>
        </div>
        <div class="col-sm"></div>
      </div>
    </div>
  </div>
</template>

<script>
import { firebase } from "@/firebase";

export default {
  name: "Login",
  data: function () {
    return {
      Email: "",
      password: "",
    };
  },
  methods: {
    login: function () {
      const user = firebase
        .auth()
        .signInWithEmailAndPassword(this.Email, this.password)
        .then((result) => {
          console.log("Uspijesna prijava");

          /* Replaces rutu na home page pa kada se vraca strelicom na proslu stranicu 
           pokaze prijasnji homepage a ne login */
          this.$router.replace({ name: "home" });
        })
        .catch(function (e) {
          console.error("Error", e);
        });
    },
  },
};
</script>
