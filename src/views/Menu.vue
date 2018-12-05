<template>
  <div>
    <HomePlan/>
    <Recipes/>
  </div>
</template>

<script>
import HomePlan from "@/components/HomePlan";
import Recipes from "@/components/Recipes";

export default {
  name: "Menu",
  components: {
    HomePlan,
    Recipes
  }
};
</script>

<style scoped>
</style>