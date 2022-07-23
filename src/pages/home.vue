<template>
  <div class="md-body">
    <p>HELLO!! I`m a HOME Page!</p>
    <div class="card__wrapper" v-for="item in items" :key="item.id">
      <Card :title="item.title" :name="`${item.lvl} lvl`" />
    </div>
  </div>
</template>

<script>
import Card from '@/components/UI/Card.vue'
export default {
  components: {
    Card
  },
  data() {
    return {
      items: [
        {
          id: 1,
          title: 'archer',
          description: 'archer archer',
          lvl: 4
        },
        {
          id: 2,
          title: 'warrior',
          description: 'warrior warrior',
          lvl: 5
        }
      ]
    }
  }
}
</script>
