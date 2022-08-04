<template>
  <NavBar class="nav" />
  <div class="center">
    <router-link to="/">Home</router-link>
    <router-link to="/about">About</router-link>
  </div>
  <router-view />
  <FooterComponent class="footer" />
</template>

<script setup>
import NavBar from "@/components/NavBar.vue";
import FooterComponent from "./components/FooterComponent.vue";
</script>

<style>
.center {
  width: 100vw;
  display: flex;
  justify-content: center;
  gap: 40px;
}
.nav {
  width: 100vw;
  display: flex;
  justify-content: center;
  background-color: #d3d3d3;
}
.footer {
  width: 100vw;
  display: flex;
  justify-content: center;
  background-color: #d3d3d3;
}
</style>
