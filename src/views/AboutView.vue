<template>
  <Header />

  <Main />

  <footer>
    <Footer />
  </footer>
</template>

<script>
import Header from "@/components/Header.vue"
import Main from "@/components/Main.vue"
import Footer from "@/components/Footer.vue";
export default {
  components: {
    Header,
    Main,
    Footer
  }
}
</script>

<style>
* {
  font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS', sans-serif;
}

footer {
  margin-top: 650px;
}
</style>