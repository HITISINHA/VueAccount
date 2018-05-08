
<template>
  <div>
    <h1>{{ msg }}</h1>
    <br/>
    <v-tabs
      v-model="active"
      color="cyan"
      dark
      slider-color="yellow"
    >
      <v-tab
        v-for="n in 3"
        :key="n"
        ripple
      >
        Item {{ n }}
      </v-tab>
      <v-tab-item
        v-for="n in 3"
        :key="n"
      >
        <v-card flat>
          <v-card-text>{{ text }}</v-card-text>
        </v-card>
      </v-tab-item>
    </v-tabs>

    <div class="text-xs-center mt-3">
      <v-btn @click.native="next">next tab</v-btn>
    </div>
  </div>
</template>

<script>
import Vue from "vue";
import Vuetify from "vuetify";
Vue.use(Vuetify);

export default {
  data() {
    return {
      active: null,
      Products: "Products",
      Services: "Services",
      ContactUs: "Contact Us"
    };
  },
  methods: {
    next() {
      const active = parseInt(this.active);
      this.active = (active < 2 ? active + 1 : 0).toString();
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h1,
h2 {
  font-weight: normal;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
