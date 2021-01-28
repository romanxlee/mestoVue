<template>
  <div id="root">
    <Header />
    <Profile
    v-on:open-popup="openPopup"
    
    />
    <PlacesList
    />
    <Popup
    v-bind:class="{ 'popup_is-opened': isOpen }"
    v-on:close-popup="closePopup"
    />
  </div>
  
</template>

<script>
import Header from '@/components/Header';
import Profile from '@/components/Profile';
import PlacesList from '@/components/PlacesList';
import Popup from '@/components/Popup';


export default {
  name: 'app',
  components: {
    Header,
    Profile,
    PlacesList, 
    Popup
  },
  data() {
    return {
      isOpen: false
    }
  },
  methods: {
    openPopup() {
      this.isOpen = true
    },
    closePopup() {
      this.isOpen = false
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
