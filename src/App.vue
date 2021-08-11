<template>
  <div id="app">
    <PhoneBook msg="Phone Book Example" />
  </div>
</template>

<script>
import PhoneBook from "./components/PhoneBook.vue";

export default {
  name: "App",
  components: {
    PhoneBook,
  },
};
</script>

<style>
* {
  margin: 0;
  padding: 0;
}

*,
*::after,
*::before {
  box-sizing: inherit;
}

html {
  box-sizing: border-box;
  font-size: 62.5%; /*1rem = 10px*/
}



body{
  font-family: Avenir, Helvetica, Arial, sans-serif;
  padding: 2rem 1rem;
}


</style>
