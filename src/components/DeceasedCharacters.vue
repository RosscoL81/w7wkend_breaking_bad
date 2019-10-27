<template lang="html">
  <div id='deceased-characters'>
    <h2>Deceased Characters</h2>
    <ul>
      <list-item
      v-for="(deceasedCharacter, index) in deceasedCharacters" :deceasedCharacter="deceasedCharacter" :key="index">
      </list-item>
    </ul>

  </div>
</template>

<script>
import ListItem from './ListItem.vue'
import CharactersList from './CharactersList.vue'
export default {
  name: 'deceased-characters',
  props: ['characters'],
  components: {
    "list-item": ListItem
  }

}
</script>

<style lang="css" scoped>
</style>
