<script setup>
// Import art.json data
import artFile from './art.json'
// Import ArtContainer component
import ArtContainer from './components/ArtContainer.vue'
// Import ArtModal component
// import ArtModal from './components/ArtModal.vue'

//

</script>

<template>
  <div class="header">
    <h1>lumey's art gallery</h1>
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
  /* Vertical Grid */
  
  font-family: "DM Sans", sans-serif;
}
.header {
  background-color: #131d26;
  height: 5vh;
  width: 100%;
  display: flex;
  justify-content: left;
  align-items: center;
  padding-left: 1rem;
  font-weight: 700;
  font-size: 25px;
  font-family: "DM Sans", sans-serif;
  color: white;
}
</style>
