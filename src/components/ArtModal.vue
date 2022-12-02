<script>
export default {
    name: 'ArtModal',
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
}

</script>
<template>
    <div class="modal">
        <div class="modalContent">
            <div class="modalHeader">
                <h1>{{ art.PrettyName }}</h1>
                <button @click="$emit('close')">
                    <img src="../assets/close.svg" alt="close" />
                </button>
            </div>
            <div class="modalBody">
                <img :src="art.image" alt="art" />
                <div class="modalText">
                    <p>{{ art.artist }}</p>
                </div>
            </div>
        </div>
    </div>
</template>
<style>
.modal {
    position: fixed;
    z-index: 1;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    overflow: auto;
    background-color: rgba(0, 0, 0, 0.4);
}
.modalContent {
    background-color: #131d26;
    margin: 15% auto;
    padding: 20px;
    border: 1px solid #888;
    width: 80%;
    height: 80%;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
}
.modalHeader {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.modalBody {
    display: flex;
    justify-content: space-between;
    align-items: center;
}
.modalText {
    display: flex;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
}
</style>