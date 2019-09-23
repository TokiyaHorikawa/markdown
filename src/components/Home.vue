<template>
  <div id="home" class="homeContent">
    <h1>{{ msg }}</h1>
    <button>Googleアカウントでログイン</button>
  </div>
</template>

<script>
export default {
  name: "home",
  data() {
    return {
      msg: "Welcom to Mymarkdown"
    }
  }
}
</script>

<style>
.homeContent {
  text-align: center;
}
</style>
