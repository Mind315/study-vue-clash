<template>
  <div class="wrapper">
    <Header />
    <div class="wrapper-content">
      <div class="container">
        <div class="view-sm isCenter">
          <router-view />
        </div>
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Footer from '@/components/Footer.vue'
import Header from './components/Header.vue'

export default {
  components: { Footer, Header }
}
</script>
<style lang="scss"></style>
