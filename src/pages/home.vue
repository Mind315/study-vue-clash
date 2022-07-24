<template>
  <div class="md-body">
    <div class="card__wrapper" v-for="item in items" :key="item.id">
      <Card :title="item.title" :name="`${item.lvl} lvl`" :imgUrl="item.img">
        {{ item.description }}
      </Card>
    </div>
  </div>
</template>

<script>
import Card from '@/components/UI/Card.vue'
import items from '@/seeders/items.js'
export default {
  components: {
    Card
  },
  data() {
    return {
      items: items
    }
  }
}
</script>
