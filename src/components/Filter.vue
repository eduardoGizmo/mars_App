<template lang="html">

  <form class="" v-on:submit.prevent >
    <select class="select-css" v-on:change="chooseRover" v-model="selectedRover">
      <option disabled value="">Select a Rover</option>
      <option value="opportunity">Opportunity</option>
      <option value="curiosity">Curiosity</option>
      <option value="spirit">Spirit</option>
    </select>
    

  </form>

</template>

<script>
import { eventBus } from '../main.js'

export default {
  name:"filterValues",
  data(){
    return {
      "selectedRover": ""
    }
  },
  methods: {
    chooseRover(){
      eventBus.$emit('roverSelected', this.selectedRover)
    }
  },
}
</script>
