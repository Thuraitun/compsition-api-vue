<template>
  <div>
    <Data />
    <DemoOne />
    <DemoTwo />
    <Method /><br>
    <VModel />
  </div>
</template>

<script>
  import Data from "./components/Data.vue"
  import DemoOne from "./components/DemoOne.vue";
  import DemoTwo from "./components/DemoTwo.vue";
  import Method from "./components/Method.vue";
  import VModel from "./components/VModel.vue";

  export default {
    name: 'App',
    components: {
      Data,
      DemoOne,
      DemoTwo,
      Method,
      VModel,
    }
    
  }
</script>

<style scoped>

</style>