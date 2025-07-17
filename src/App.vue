<template>
  <div id="app">
    <app-header></app-header>
    <app-nav></app-nav>
    <router-view></router-view>
    <app-footer></app-footer>
  </div>
</template>

<script>
import Header from './components/header.vue'
import Nav from './components/nav.vue'
import Article from './components/article.vue'
import Footer from './components/footer.vue'

export default {
  components: {
    'app-header': Header,
    'app-nav': Nav,
    'app-article': Article,
    'app-footer': Footer
  },
  name: 'app',
  data () {
    return {

    }
  }
}
</script>

<style scoped>

</style>
