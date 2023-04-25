<template>
  <div class="container">
    <img src="/images/tryme.gif" alt="" class="background-image">
    <div class="button-container">
      <router-link to="/about" class="button">Listen To Music</router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: "HomePage",
  mounted() {
    window.scrollTo(0, document.body.scrollHeight / 3);
  }
};
</script>

<style>
body{
  background-color: #053754;
}
.container {
  position: relative;
  width: 100%;
  height: 100vh;
}

.background-image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.button-container {
  position: absolute;
  left: 50%;
  top: 70%;
  transform: translate(-50%, -50%);
}

.button {
  display: inline-block;
  padding: 16px 32px;
  border-radius: 4px;
  background-color:none;
  color: #fff;
  font-size: 18px;
  text-align: center;
  text-decoration: none;
  box-shadow:  0 0 10px white , 0 0 20px aqua;
}

.button:hover {
  transition: 1s;
  background-color: #0f6a83;
}
audio{
  display: none;
}
@media (max-width:500px){
  .button{
    width: 200px;
  }
}
</style>
