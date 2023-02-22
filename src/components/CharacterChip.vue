<script>
import { defineProps, defineEmits, defineExpose, defineComponent } from 'vue'
export default defineComponent({
    name: 'CharacterChip',
    props: {
        character: {
            type: Object,
            required: true
        }
    },
    setup(props) {
        return {
            props
        }
    }
})


</script>
<template>
    <div class="character-chip" :style="{outlineColor: character.mainColor}">
        <div class="character-chip-image">
            <img :src="character.picture" :alt="character.name" />
        </div>
        <div class="character-chip-text">
            <h2>{{ character.name }}</h2>
        </div>
    </div>
</template>
<style scoped>
/* a small rounded chip with the image on the left, and text on the right, and the image should be at a 1:1 ratio. the height should be slightly shorter than the parent div*/
.character-chip {
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: flex-start;
    border-radius: 100vh;
    outline-style: solid;
    outline-width: 2px;
    outline-offset: 2px;
    margin: 1rem;
    padding: 5px;
    padding-left: 2px;
    width: fit-content;
    height: fit-content;
    /* make it so the image doesn't stretch out the box */
     max-width: 100%; 
     max-height: 50%; 
    transition: cubic-bezier(0.075, 0.82, 0.165, 1) 0.3s;
}
/* the image should not be bigger than the chip */
.character-chip-image {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    width: 25px;
    height: 25px;
    /* make it so the image doesn't stretch out the box */
    max-width: 100%; 
    max-height: 100%; 
    object-fit: cover;
}

.character-chip-image img {
    /* make it so the image doesn't stretch out the box */
    width: 25px;
    height: 25px;
    max-width: 100%; 
    max-height: 100%; 
    border-radius: 100vh;
    object-fit: cover;
    object-position: center center;
}
.character-chip-text {
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: flex-start;
    padding-left: 10px;
    user-select: none;
}
h2 {
    font-family: "DM Sans", sans-serif;
    font-weight: 700;
    font-size: 1rem;
}

.character-chip:hover {
   transform: scale(1.1);
}

</style>