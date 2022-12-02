<script>
import { defineProps, defineEmits, defineExpose, defineComponent } from 'vue'
export default defineComponent({
    name: 'ArtContainer',
    props: {
        art: {
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
<script setup>
import { onMounted } from 'vue'
onMounted(() => {
    function openModal() {
        showModal = true
    }
var image = document.getElementById('container')
image.onclick = function() {
    openModal();
};
});


</script>

<template>
    <!-- Art caption -->
    <div class="container">
        <img class="art-image" :src="art.file" alt="art image" />
        <div class="art-caption">
            <h2 style="font-weight: 700;">{{ art.prettyName }}</h2>
            <p>Artist: <a :href="art.artistLink">{{art.artist}}</a></p>
        </div>
    </div>

    <!-- Art image -->



</template>
<style scoped>
.template {
    width: 10vw;
    height: 10vh;
}

.container {
    position: relative;
    text-align: center;
    color: white;
}
a {
    color: #bcdceb;
}
.art-caption {
    /* display: flex; */
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    text-align: center;
    font-family: "DM Sans", sans-serif;
    opacity: 0;
    color: white;
    border: #bcdceb 1px solid;
    text-shadow:
   -1px -1px 0 #131d26,  
    1px -1px 0 #131d26,
    -1px 1px 0 #131d26,
     1px 1px 0 #131d26;

    /* Center in the div */
    position: absolute;
    top: 80%;
    left: 50%;
    transform: translate(-50%, -50%);
    /* Blur the caption area */
    backdrop-filter: blur(10px);
    border-radius: 1rem;
    /* Fade in the caption */
    transition: opacity 0.1s ease-in-out;
}

/* Only show the caption on hover of image or caption */
.container:hover .art-caption,
.art-caption:hover {
    opacity: 1;
}

.art-image {
    display: flex;
    justify-content: center;
    align-items: center;
    padding: 1rem;
    border-radius: 3rem;
    max-width: 100%;
    max-height: 100%;


}


</style>