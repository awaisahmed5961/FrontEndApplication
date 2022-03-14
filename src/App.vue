<template>
  <div>
    <div class="row">
      <div class="col-sm-12 col-md-3 col-lg-2">
        <SideBar />
      </div>
      <div class="col-sm-12 col-md-9 col-lg-10">
        <Main />
      </div>
    </div>
  </div>
</template>

<script>
import Main from "./components/Layout/Main.vue";
import SideBar from "./components/Layout/SideBar.vue";

export default {
  name: "App",
  components: {
    Main,
    SideBar,
  },
};
</script>

<style>
</style>
