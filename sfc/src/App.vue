<template>
  <div id="app">
    <CommunityLogo :msg="message"/>
    <input v-model="message" placeholder="edit me">
  </div>
</template>

<script>
import CommunityLogo from './components/CommunityLogo.vue'

export default {
  name: 'app',
  components: {
      CommunityLogo
  },
    data() {
      return {
          message: 'COMMUNITY BAYERN'
      }
    }
}
</script>

<style>
</style>
