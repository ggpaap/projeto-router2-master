<script setup>
import HeaderComp from "@/components/template/HeaderComp.vue";
import FooterComp from "@/components/template/FooterComp.vue";
</script>

<template>
  <header-comp />
  <main>
    <RouterView />
  </main>
  <Footer-comp />
</template>

<style>
@import url("https://fonts.googleapis.com/css2?family=Cormorant+Garamond&display=swap");

body {
  background-color: #4f374d;
}

#app {
  max-width: 1280px;
  margin: 0 auto;
  font-weight: normal;
  height: 100vh;
}

main {
  height: 80%;
}

a {
  color: inherit;
  text-decoration: none;
}

.router-link-active {
  color: #98b7e1;
}
</style>
