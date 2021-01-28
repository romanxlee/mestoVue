<template>
    <div class="popup">
        <div class="popup__content">
            <img 
            v-on:click="$emit('close-popup')"
            src="../assets/close.svg" alt="" class="popup__close">
            <h3 class="popup__title">Новое место</h3>
            <form 
            v-on:change=" isActive=true "
            v-on:submit.prevent="onSubmit"
            class="popup__form" name="new" novalidate>
                <input 
                v-model="name"
                name="name" class="popup__input popup__input_type_name" placeholder="Название" >

                <input 
                v-model="link"
                name="name" class="popup__input popup__input_type_link-url" placeholder="Ссылка на картинку">
                <button 
                class="button popup__button"
                v-bind:class="{ 'popup__button_active':isActive}">+</button>
            </form>
        </div>
    </div>
</template>

<script>
export default {
    data() {
        return {
            name: '',
            link: '',
            isActive: false
        }
    },
    methods: {
        onSubmit() {
            if (this.name.trim() && this.link.trim()) {
                const newCard = {
                    id: Date.now(),
                    name: this.name,
                    link: this.link
                }

                this.$emit('add-card', newCard)
                this.name = ''
                this.link = ''
            } 
        }
    }
}
</script>

<style>
.popup {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    background-color: rgba(0,0,0,.5);
    align-items: center;
    justify-content: center;
    display: none;
}

.popup.popup_is-opened {
    display: flex;
}

.popup__content {
    width: 430px;
    min-height: 330px;
    position: relative;
    box-sizing: border-box;
    padding: 34px 36px;
    background-color: #fff;
    border-radius: 10px;
}

.popup__close {
    width: 26px;
    position: absolute;
    top: -26px;
    right: -26px;
    cursor: pointer;
}

.popup__title {
    margin: 0;
    font-size: 24px;
    line-height: 30px;
}

.popup__form {
    margin-top: 60px;
}

.popup__input {
    width: 100%;
    height: 47px;
    border: 0;
    border-bottom: 1px solid rgba(0,0,0,.2);
    font-size: 14px;
    line-height: 17px;
    box-sizing: border-box;
    padding: 5px 6px 13px;
    margin-bottom: 24px;
}

.popup__input:last-of-type {
    margin-bottom: 0;
}

.popup__button {
    width: 100%;
    height: 50px;
    border: 1px solid rgba(0,0,0,.2);
    margin-top: 48px;
    color: rgba(0,0,0,.2);
    font-size: 36px;
}

.popup__button.popup__button_active {
    background-color: #000;
    color: #fff;
}
</style>