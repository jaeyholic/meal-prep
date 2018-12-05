<template>
  <v-container grid-list-lg>
    <v-layout row>
      <v-flex xs12 class="text-xs-center display-1 font-weight-black my-5">Available Meal Plans</v-flex>
    </v-layout>
    <v-layout row wrap>
      <v-flex xs12 sm12 md4 v-for="detail in details" :key="detail.title">
        <v-card>
          <v-responsive>
            <v-img :src="detail.img" height="500px">
              <v-container fill-height fluid>
                <v-layout fill-height>
                  <v-flex xs12 align-end flexbox>
                    <span class="headline white--text">{{ detail.title }}</span>
                  </v-flex>
                </v-layout>
              </v-container>
            </v-img>
          </v-responsive>

          <v-card-text primary-title>
            <div>
              <h3 class="headline mb-0">{{detail.subtitle }}</h3>
              <div>{{ detail.content }}</div>
            </div>
          </v-card-text>

          <v-card-actions v-if="['menu'].includes($route.name)">
            <v-btn
              outline
              block
              color="green"
              @click="showRecipes('detail.subtitle')"
            >Select This Plan</v-btn>
          </v-card-actions>
        </v-card>
      </v-flex>
    </v-layout>
  </v-container>
</template>

<script>
export default {
  name: "HomePlan",
  data() {
    return {
      details: [
        {
          img: "http://source.unsplash.com/hjCA3ecCXAQ",
          title: "KETO",
          subtitle: "Keto",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam mauris felis, varius rutrum massa a, dignissim ornare dui. Cras eget velit eu dui tristique lobortis sit amet vel tellus."
        },
        {
          img: "http://source.unsplash.com/6S27S6pZ6o0",
          title: "PALEO",
          subtitle: "Paleo",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam mauris felis, varius rutrum massa a, dignissim ornare dui. Cras eget velit eu dui tristique lobortis sit amet vel tellus."
        },
        {
          img: "http://source.unsplash.com/1SPu0KT-Ejg",
          title: "VEGAN",
          subtitle: "Vegan",
          content:
            "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Nullam mauris felis, varius rutrum massa a, dignissim ornare dui. Cras eget velit eu dui tristique lobortis sit amet vel tellus."
        }
      ]
    };
  },
  methods: {
    showRecipes(plan) {
      this.$store.dispatch("getRecipes", plan);
    }
  }
};
</script>

<style scoped>
</style>