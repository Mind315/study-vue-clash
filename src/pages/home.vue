<template>
  <carousel :settings="settings" :breakpoints="breakpoints">
    <!-- ------------------- -->
    <slide class="card__wrapper" v-for="item in items" :key="item.id">
      <Card
        :title="item.title"
        :name="`${item.lvl} lvl`"
        :imgUrl="item.img"
        :link="`/${item.alias}`"
      >
        <template v-slot:body> {{ item.description }} </template>
        <template v-slot:footer>
          <div class="card-stats">
            <div
              v-for="(stat, index) in item.info"
              :key="index"
              class="one-third"
            >
              <div class="stat-value">{{ stat.value }}</div>
              <div class="stat">{{ stat.title }}</div>
            </div>
          </div>
        </template>
      </Card>
    </slide>
    <template #addons>
      <navigation />
    </template>
  </carousel>
</template>

<script>
import Card from '@/components/UI/Card.vue'
import items from '@/seeders/items.js'

// If you are using PurgeCSS, make sure to whitelist the carousel CSS classes
import 'vue3-carousel/dist/carousel.css'
import { Carousel, Slide, Navigation } from 'vue3-carousel'
export default {
  components: {
    Card,
    Carousel,
    Slide,
    Navigation
  },
  data() {
    return {
      items: items,
      settings: {
        itemsToShow: 2,
        wrapAround: true,
        snapAlign: 'center'
      },
      breakpoints: {
        300: {
          itemsToShow: 1
        },
        700: {
          itemsToShow: 2
        },
        1200: {
          itemsToShow: 3
        }
      }
    }
  }
}
</script>
