<template>
  <div id="home" class="homeContent">
    <h1>{{ msg }}</h1>
    <button @click="googleLogin">Googleアカウントでログイン</button>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      msg: "Welcom to Mymarkdown"
    }
  },
  methods: {
    googleLogin: function () {
      firebase
        .auth()
        .signInWithRedirect(new firebase.auth.GoogleAuthProvider())
    }
  }
}
</script>

<style>
.homeContent {
  text-align: center;
}
</style>
