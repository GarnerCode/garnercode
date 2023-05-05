<template>
  <div id="home-page">
    <Landing></Landing>
    <About></About>
    <Tech></Tech>
    <Experience></Experience>
    <Reviews></Reviews>
    <Portfolio></Portfolio>
    <Contact></Contact>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'
import AOS from 'aos'
import 'aos/dist/aos.css'

export default Vue.extend({
  name: 'IndexPage',
  mounted() {
    AOS.init();
  }
})
</script>
