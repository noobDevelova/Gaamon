<template>
  <!-- <NavbarNav /> -->
  <router-view />
</template>
<script>
// import NavbarNav from "./components/navbar/NavbarNav.vue";
export default {
  components: {
    // NavbarNav,
  },
};
</script>
<style lang="scss">
@import "./assets/scss/variables.scss";
body {
  font-family: $archivo;
  box-sizing: border-box;
}
</style>
