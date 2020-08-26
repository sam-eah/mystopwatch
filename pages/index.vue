<template>
  <v-container>
  <v-row justify="center" align="center">
    <v-col cols="12">
      <v-btn @click="generate">Generate</v-btn>
    </v-col>
    <v-col cols="12">
      <n-link :to="datenow" v-if="clicked">
        <a>myawesomeadress/{{datenow}}</a>
      </n-link>
    </v-col>
  </v-row>
  </v-container>
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
