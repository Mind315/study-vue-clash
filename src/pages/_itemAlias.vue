<template>
  <div class="wrapper-person">
    <div v-if="item">
      <img :src="item.img" :alt="item.description" />
      <h1 style="color:white;" class="title">{{ item.title }}</h1>
      <p>{{ item.description }}</p>

      <div class="card-stats">
        <div v-for="(stat, index) in item.info" :key="index" class="one-third">
          <div class="stat-value">{{ stat.value }}</div>
          <div class="stat">{{ stat.title }}</div>
        </div>
      </div>
      <br />
      <router-link to="/" class="btn btnPrimary">Back to Home</router-link>
    </div>
  </div>
</template>

<script>
import items from '@/seeders/items'

export default {
  data() {
    return {
      item: null
    }
  },
  created() {
    const alias = this.$route.params.itemAlias
    const item = items.find(el => el.alias === alias)

    this.item = item
  }
}
</script>

<style lang="scss">
.wrapper-person {
  text-align: center;
  .card-stats {
    margin: 30px 0;
    border-radius: 14px;
  }
}
</style>
