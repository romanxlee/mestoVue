<template>
    <div class="img-popup">
        <div class="img-popup__content">
            <img 
            @click="$emit('close-image')"
            src="../assets/close.svg" alt="" class="img-popup__close">
            <img class="img-popup__place"
            v-bind:src="link">
        </div>
    </div>
</template>

<script>
export default {
    props: {
        link : {
            type: String
        }
    }
}
</script>

<style>
.img-popup {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0, 0, 0, .5);
    align-items: center;
    justify-content: center;
    display: none;
}

.img-popup.img-popup_is-opened {
    display: flex;
}

.img-popup__content {
    position: relative;
}

.img-popup__close {
    width: 26px;
    position: absolute;
    top: -26px;
    right: -26px;
    cursor: pointer;
}

.img-popup__place {
    max-width: 80vw;
    max-height: 80vh;
}
</style>