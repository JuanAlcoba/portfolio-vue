<template>
  <div>
    <NavBar />
    <hello-world />
  </div>
</template>

<script>
import HelloWorld from "../components/HelloWorld";
import NavBar from "../components/NavBar";


export default {
  name: "HomeVue",

  components: {
    HelloWorld,
    NavBar
    
  },
};
</script>
