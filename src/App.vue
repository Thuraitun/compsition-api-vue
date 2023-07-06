<template>
  <div>
    <Data />
    <DemoOne />
    <DemoTwo />
    <Method /><br>
    <VModel /><br><br>
    <Computed />
    <Watch />
    <ProvideInject />
    <TemplateRef /><br>
    <Person />
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
  import ProvideInject from "./components/ProvideInject.vue";
  import TemplateRef from "./components/TemplateRef.vue";
  import Person from "./components/Person.vue";

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
      ProvideInject,
      TemplateRef,
      Person,
    }
    
  }
</script>

<style scoped>

</style>