<template>
  <header class="card">
    <h1>لیست وظایف </h1>

    <button @click="changeTheme" id="theme-switcher">
      <img v-if="defaultTheme=='dark'" :src="sunImage" alt="Change color theme" />
      <img v-else :src="moonImage" alt="Change color theme" />
    </button>
  </header>
</template>

<script>
import Sun from "../assets/images/icon-sun.svg";
import Moon from "../assets/images/icon-moon.svg";
export default 
{
  name:"AppHeader",
  data() {
    return {
      sunImage:Sun,
      moonImage:Moon,
      defaultTheme:"dark",
    };
  },
  methods: {
    changeTheme(){
      if (this.defaultTheme=="dark") {
        this.defaultTheme="light";
        document.querySelector("body").classList.add("light");
      } else {
        this.defaultTheme="dark";
        document.querySelector("body").classList.remove("light");

      }
    }
  },

};

</script>