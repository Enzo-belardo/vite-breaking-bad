<script>
import appHeader from './components/appHeader.vue';
import appMain from './components/appMain.vue';

export default {
  name: 'AppYuGiOh',
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
@use './styles/general.scss' as * ;
@use './styles/partials/variables' as * ;

</style>
