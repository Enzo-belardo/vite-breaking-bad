<script>
import { store } from './store.js'
import appHeader from './components/appHeader.vue';
import appMain from './components/appMain.vue';

export default {
  name: 'AppVue',
  components: {
    appHeader,
    appMain,
  }
}

</script>

<template>
  <appHeader/>
  <appMain/>
</template>

<style lang="scss">
@use './styles/general' as * ;
@use './styles/partials/variables' as * ;
@use "bootstrap/scss/bootstrap" as *;

</style>
