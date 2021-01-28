<template>
    <div class="place-card">
        <div 
        v-bind:style="{backgroundImage: 'url(' + item.link + ')'}" 
        class="place-card__image">
            <button 
            v-on:click="$emit('remove-card', item.id)"
            class="place-card__delete-icon"></button>
        </div>
        <div class="place-card__description">
            <h3 class="place-card__name">{{ item.name }}</h3>
            <button
            v-on:click="e => e.target.classList.toggle('place-card__like-icon_liked')"
            class="place-card__like-icon"></button>
        </div>
    </div>
</template>

<script>
export default {
    props: {
        item: {
            type: Object
        }
    }
}
</script>

<style>
 .place-card {
    width: 282px;
    min-height: 360px;
    background-color: #fff;
    border-radius: 10px;
}

.place-card__image {
    background-size: cover;
    background-position: 50%;
    position: relative;
    cursor: pointer;
    background-image: url(../assets/avatar.jpg);
}

.place-card__image, .place-card__image:after {
    height: 282px;
    border-top-left-radius: 10px;
    border-top-right-radius: 10px;
}

.place-card__description {
    display: flex;
    min-height: 78px;
    align-items: center;
    justify-content: space-between;
    box-sizing: border-box;
    padding: 0 22px;
}

.place-card__delete-icon {
    background: url(../assets/trash-icon.svg) 50% no-repeat;
    background-color: transparent;
    border: none;
    width: 18px;
    height: 20px;
    position: absolute;
    top: 18px;
    right: 15px;
    cursor: pointer;
    outline: none;
}

.place-card__name {
    margin: 0;
    font-size: 24px;
    line-height: 29px;
}

.place-card__like-icon {
    background: url(../assets/like-inactive.svg) 50% no-repeat;
    background-color: transparent;
    border: none;
    width: 21px;
    height: 19px;
    cursor: pointer;
    transition: transform .3s linear;
    outline: none;
}

.place-card__like-icon_liked {
  background-image: url(../assets/like-active.svg);
}
</style>