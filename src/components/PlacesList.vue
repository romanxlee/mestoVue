<template>
    <div 
    
    class="places-list root__section">
      <Card 
      v-bind:initial="initial"
      v-for="item in initial"
      :item="item"
      :key="item.id"
      v-on:remove-card="emitData"
      />
    </div>
</template>

<script>
import Card from '@/components/Card';

export default {
    props: ['initial'],
    components: {
    Card
  },

    methods: {
        removeCard(id) {
            this.initial = this.initial.filter(item => item.id !== id)
        },
        emitData(id) {
          this.$emit('delete', id)
        }
    }
}
</script>