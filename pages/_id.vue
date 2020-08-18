<template>
  <v-layout column justify-center align-center>
    <v-flex xs12 sm8 md6>
        <h1>Commencé à : {{ beginTime }}</h1>
        <h1>Temps écoulé : {{ stopwatch }}, Coût : {{ price }} €</h1>
    </v-flex>
  </v-layout>
</template>

<script>
import moment from 'moment';

export default {
  data() {
    return {
      id: this.$route.params.id,
      timePassed: 0,
      timerInterval: null,
      beginTime : moment(this.id).format('HH : mm : ss')
    };
  },
  methods: {
    startTimer() {
      this.timerInterval = setInterval(() => {
          this.timePassed = Date.now() - this.id
          return this.timePassed
        }, 10);
    }
  },
  computed: {
    stopwatch () {
        // console.log(this.timePassed)
      return moment(this.timePassed).format('mm : ss');
    },
    price () {
        return moment(this.timePassed).minutes() * 2
    }
  },
//   watch: {
//     timePassed(newValue) {
//       if (newValue === 0) {
//         // this.onTimesUp();
//       }
//     }
//   },
  mounted() {
      this.startTimer()
  }
};
</script>
