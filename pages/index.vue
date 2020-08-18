<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
      <v-btn @click="generate">Generate</v-btn>

      <n-link tag="li" :to="datenow" v-if="clicked">
        <a>myawesomeadress/{{datenow}}</a>
      </n-link>
    </v-flex>
  </v-layout>
</template>



<script>
export default {
  data: function () {
    return {
      clicked: false,
      datenow: "",
    };
  },
  methods: {
    generate(event) {
      console.log(Date.now());
      this.clicked = true;
      this.datenow = Date.now().toString()
    },
  },
};
</script>
