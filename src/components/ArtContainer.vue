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

<template>
    <!-- Art caption -->
    <div class="container" v-viewer.static="{toolbar: false, navbar: false}">
        <img class="art-image" :src="art.file" :alt="art.prettyName" />
        <div class="art-caption">
            <h2 style="font-weight: 700;">{{ art.prettyName }}</h2>
            <p>Artist: <a :href="art.artistLink">{{art.artist}}</a></p>
        </div>
    </div>

    <!-- Art image -->



</template>
<style scoped>
.template {
    max-width: 10vw;
    max-height: 10vh;
}

.container {
    position: relative;
    text-align: center;
    color: white;
    /* make this fit on screen on mobile devices */
    height: fit-content;
    max-width: 100%;
    max-height: 100%;
    display: inline-block;

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
    /* Center this image vertically and horizontally */
    display: block;
    margin-left: auto;
    margin-right: auto;
    object-fit: contain;
    border-radius: 1rem;
    max-width: 100%;
    max-height: 100%;




}


</style>