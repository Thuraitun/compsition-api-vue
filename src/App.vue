<template>
  <div>
    <Data />
    <DemoOne />
    <DemoTwo />
    <Method /><br>
    <VModel /><br><br>
    <Computed />
    <Watch />
  </div>
</template>

<script>
  import Data from "./components/Data.vue"
  import DemoOne from "./components/DemoOne.vue";
  import DemoTwo from "./components/DemoTwo.vue";
  import Method from "./components/Method.vue";
  import VModel from "./components/VModel.vue";
  import Computed from "./components/Computed.vue";
  import Watch from "./components/Watch.vue";

  export default {
    name: 'App',
    components: {
      Data,
      DemoOne,
      DemoTwo,
      Method,
      VModel,
      Computed,
      Watch,

    }
    
  }
</script>

<style scoped>

</style>