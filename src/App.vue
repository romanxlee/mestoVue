<template>
  <div id="root">
    <Header />
    <Profile
    v-on:open-popup="togglePopup"
    
    />
    <PlacesList
    v-bind:initial="initial"
    v-on:delete="removeCard"
    v-on:open-image="openImage"
    />
    <Popup
    v-bind:class="{ 'popup_is-opened': isOpen }"
    v-on:close-popup="togglePopup"
    v-on:add-card="addCard"
    />
    <ImagePopup
    v-bind:link="link"
    v-bind:class="{ 'img-popup_is-opened': imageOpen }"
    @close-image="openImage"
    />
  </div>
  
</template>

<script>
import Header from '@/components/Header';
import Profile from '@/components/Profile';
import PlacesList from '@/components/PlacesList';
import Popup from '@/components/Popup';
import ImagePopup from '@/components/ImagePopup';


export default {
  name: 'App',
  components: {
    Header,
    Profile,
    PlacesList, 
    Popup,
    ImagePopup
  },
    methods: {
    togglePopup() {
      this.isOpen = !this.isOpen
    },
    addCard(item) {
      this.initial.push(item)
      this.togglePopup()
    },
    removeCard(id) {
    this.initial = this.initial.filter(item => item.id !== id)
    },
    openImage(src) {
      this.imageOpen = !this.imageOpen
      this.link = src
    }
  },
  data() {
    return {
      isOpen: false,
      imageOpen: false,
      link: '',
      initial: [
    {
      id:1,
      name: 'Архыз',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/arkhyz.jpg'
    },
    {
      id: 2,
      name: 'Челябинская область',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/chelyabinsk-oblast.jpg'
    },
    {
      id: 3,
      name: 'Иваново',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/ivanovo.jpg'
    },
    {
      id: 4,
      name: 'Камчатка',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/kamchatka.jpg'
    },
    {
      id: 5,
      name: 'Холмогорский район',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/kholmogorsky-rayon.jpg'
    },
    {
      id: 6,
      name: 'Байкал',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/baikal.jpg'
    },
    {
      id: 7,
      name: 'Нургуш',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/khrebet-nurgush.jpg'
    },
    {
      id: 8,
      name: 'Тулиновка',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/tulinovka.jpg'
    },
    {
      id: 9,
      name: 'Остров Желтухина',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/zheltukhin-island.jpg'
    },
    {
      id: 10,
      name: 'Владивосток',
      link: 'https://pictures.s3.yandex.net/frontend-developer/cards-compressed/vladivostok.jpg'
     }
  ]
    }
  }
}


</script>

<style>
#root {
    background-color: #000;
    min-height: 100vh;
    font-family: Inter;
    padding-bottom: 194px;
    -webkit-font-smoothing: antialiased;
}

.root__section {
    width: calc(100% - 400px);
    margin: auto;
}

.places-list {
    display: grid;
    grid-template-columns: repeat(auto-fill,282px);
    grid-gap: 18px 18px;
    justify-content: center;
}
</style>
