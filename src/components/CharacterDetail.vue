<template lang="html">
  <div v-if="character" id="characterDetail">
    <h2>{{character.name}}</h2>
    <div>
      <p>Nickname: {{character.nickname}}</p>
      <p>Status: {{character.status}}</p>
      <p>Actor's name: {{character.portrayed}}</p>
      <img :src="character.img" :alt="character.name">
    </div>

  </div>

</template>

<script>

export default {
  name: 'character-detail',
  props: ['character'],
}
</script>

<style lang="css" scoped>
img {
  height: 200px;
}
</style>
