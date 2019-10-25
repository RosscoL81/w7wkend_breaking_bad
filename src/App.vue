<template lang="html">
  <div>
    <div class="main container">
      <characters-list :characters="characters"></characters-list>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import CharactersList from './components/CharactersList.vue'

export default {
  name: 'app',
  data() {
    return {
      characters: []
    }
  },
  components: {
    "characters-list": CharactersList,
  },

  mounted() {
    fetch("https://www.breakingbadapi.com/api/characters")
    .then(response => response.json())
    .then(characters => this.characters = characters)
  }
}
</script>

<style lang="css" scoped>


</style>
