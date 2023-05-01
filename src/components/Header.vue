<template>
  <div class="headerbuttons">
    <button class="toggle" @click="toggle()">Open The Bar</button>
  </div>
  <header v-if="show">
    <router-link to="/about">Music Type</router-link>
    <router-link to="/about">Music Type</router-link>
    <router-link to="/about">Music Type</router-link>
    <RouterView />
  </header>
</template>
<script>
export default {
  data() {
    return {
      show: false
    }
  },
  methods: {
    toggle() {
      this.show = !this.show
    }
  }
}
</script>

<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header {
  width: 100%;
  border: 1px solid white;
  display: flex;
  justify-content: center;
  text-align: center;
  align-items: center;
  padding: 10px;
}



.toggle {
  width: 10%;
  height: 30px;
  border: none;
  background: none;
  box-shadow: 0 0 2px white, 0 0 10px #053754;
  color: white;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 10px;
  margin-left: 44.5%;
  border-radius: 10px;

}

a {
  color: white;
  margin: 15px;
  text-decoration: none;
}

@media (max-width:500px) {
  .toggle {
    width: 25%;
    margin-left: 37%;
  }
}
</style>


