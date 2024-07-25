<template>
  <div id="app">
    <MainContainer>
    </MainContainer>
  </div>
</template>

<script>
import MainContainer from './components/MainContainer.vue'
export default {
  name: 'App',
  components: {
          MainContainer,
  }
}
</script>

<style lang="sass">

  *
    margin: 0
    padding: 0
    box-sizing: border-box
</style>
