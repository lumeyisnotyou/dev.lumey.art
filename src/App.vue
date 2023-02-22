<script setup>
// Import json data
import artFile from './art.json'
import characters from './characters.json'
// Import ArtContainer component
import ArtContainer from './components/ArtContainer.vue'
// Import characterChip component
import CharacterChip from './components/CharacterChip.vue'




</script>

<template>
  <div class="header">
    <h1>lumey's art gallery</h1>
    <!-- character selector -->
    <div class="character-selector">
      <CharacterChip v-for="character in characters" :key="character.name" :character="character" @click="showArt(character)" />
    </div>
  </div>
  <div class="artgrid">
    
      <ArtContainer v-for="art in artFile" :key="art.title" :art="art" />
  
    <!-- Show Art Modal on click of an ArtContainer -->
    <!-- <ArtModal v-if="showModal" :art="selectedArt" @close="showModal = false" /> -->
    </div>
</template>

<style scoped>
.artgrid {
  /* Horizontal Grid */
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(500px, 1fr));
  grid-gap: 1rem;
  grid-auto-flow: row;
  padding: 1rem;
  /* Vertical Grid */
  
  font-family: "DM Sans", sans-serif;
}


.header {
  background-color: #131d26;
  height: 5vh;
  width: 100%;
  display: flex;
  justify-content: flex-start;
  white-space: nowrap;
  align-items: center;
  padding-left: 1rem;
  font-weight: 700;
  font-size: 25px;
  font-family: "DM Sans", sans-serif;
  color: white;
}
/* justify the selector to the right and center it vertically */
.character-selector {
  display: flex;
  justify-content: flex-end;
  align-items: center;
  width: 100%;
  height: 75%;
  padding: 1rem;
}
</style>
<script>

// sort art objects by character
const artByCharacter = (character) => {
  return artFile.filter(art => art.character === character.title)
}

// on pressing a character chip, replace the art grid with the art of that character
const showArt = (character) => {
 console.log(artByCharacter(character))
}
</script>

