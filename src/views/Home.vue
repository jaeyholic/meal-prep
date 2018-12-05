<template>
  <span>
    <HomeHero/>
    <HomeDetails/>
    <HomePlan/>
  </span>
</template>

<script>
// @ is an alias to /src
import HomeHero from "@/components/HomeHero";
import HomeDetails from "@/components/HomeDetails";
import HomePlan from "@/components/HomePlan";
export default {
  name: "home",
  components: {
    HomeHero,
    HomeDetails,
    HomePlan
  }
};
</script>
