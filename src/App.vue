<template lang="html">
  <div>
    <div class="main-container">
      <h1>Breaking Bad Characters</h1>
      <characters-list :characters="characters"></characters-list>
      <character-detail :character="selectedCharacter"></character-detail>
      <deceased-characters :deceased-characters="deceasedCharacters"></deceased-characters>
    </div>
  </div>
</template>

<script>
import {eventBus} from './main.js'
import CharactersList from './components/CharactersList.vue'
import CharacterDetail from './components/CharacterDetail.vue'
import DeceasedCharacters from './components/DeceasedCharacters.vue'

export default {
  name: 'app',
  data() {
    return {
      characters: [],
      selectedCharacter: null,

    }
  },


  components: {
    "characters-list": CharactersList,
    "character-detail": CharacterDetail,
    "deceased-characters": DeceasedCharacters,
  },

  methods: {
      deceasedCharacters: function(){
        return this.characters.filter((character) => {
          return character.status === "deceased";

        })
      }
    },

  mounted() {
    fetch("https://www.breakingbadapi.com/api/characters")
    .then(response => response.json())
    .then(characters => this.characters = characters)
    eventBus.$on('character-selected', (character) => this.selectedCharacter = character)
  }
}
</script>

<style lang="css" scoped>

.main-container {

}
</style>
