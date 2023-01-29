<template>
  <v-row>
    <v-list v-for="key in fizzBuzzData" :key=key cols="12">
      <v-col>
        <v-list-item>
          <v-list-item-action>
            <v-icon>{{key.count}} => {{ key.item }}</v-icon>
          </v-list-item-action>
        </v-list-item>
      </v-col>
    </v-list>
  </v-row>
</template>

<script>

  export default {
    name: 'FizzBuzz',
    mounted() {
      this.startFizzBuzz()
    },

    methods: {
      startFizzBuzz() {
        // On commence à 1, 0 modulo un chiffre/nombre renverra toujours 0
        for (let i = 1; i < this.fizzBuzzCounter; i++) {
          let data = {};
          if (i % 15 == 0) {
              data.item = "FizzBuzz";
          } else if (i % 3 == 0) {
              data.item = "Fizz";
          } else if (i % 5 == 0) {
              data.item = "Buzz";
          } else {
              data.item = i;
          }
          data.count = i;
          this.fizzBuzzData.push(data);
        }
      }
    },

    data: () => ({
      fizzBuzzCounter: 100,
      fizzBuzzData: []
    })
  };

</script>
