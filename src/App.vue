<script setup>
import WouldYouRather from './components/./WouldYouRather.vue'

// object syntax
import { ref } from 'vue'

const wyrQuestion = ref('Would you rather become five years older or two years younger?')
const wyrAnswer1 = ref('Five Years Older')
const wyrAnswer2 = ref('Two Years Younger')

// This will store the users answer after they make choice
const userSelection = ref('')
function updateUserSelection(userChoice) {
  userSelection.value = `Thanks! You chose: ${userChoice}`
}

</script>

<template>

  <div id="app-component">
  <h1>Would You Rather?</h1>

<!--  This is referencing the child component, Would You Rather-->
<!--  May see this is would-you-rather, but use the one that I am here so its easier-->
  <WouldYouRather
      v-bind:question="wyrQuestion"
      v-bind:answer1="wyrAnswer1"
      v-bind:answer2="wyrAnswer2"
      v-on:choice-selected="updateUserSelection"
  >
  </WouldYouRather>


<p> {{ userSelection}} </p>

  </div>

</template>

<!-- These will affect the child component, because this is the parent-->
<style scoped>
p {
  font-family: Gadugi;
}

#app-component {
  background-color: blue;
  padding: 40px;
}


</style>
