<template>
    <div 
    v-on:remove-card="removeCard"
    class="places-list root__section">
      <Card 
      v-bind:initial="initial"
      v-for="item in initial"
      :item="item"
      :key="item.id"
      v-on:remove-card="removeCard"
      v-on:add-card="addCard"
      />
    </div>
</template>

<script>
import Card from '@/components/Card';

export default {
    components: {
    Card
  },

    methods: {
        removeCard(id) {
            this.initial = this.initial.filter(item => item.id !== id)
        },
        addCard(item) {
          this.initial.push(item)
        }
    },
    data() {
      return {
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