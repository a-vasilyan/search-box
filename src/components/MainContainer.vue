<template>
  <section class="container">
    <MainBlock></MainBlock>
    <img :src="dc" alt="">
  </section>
</template>

<script>
import MainBlock from './MainBlock.vue';
import dc from '../assets/Images/Group.png'

export default {
  data(){
    return{
      dc
    }
  },
    components:{
        MainBlock
    }
};
</script>


<style lang="sass" scoped>
.container
    background-color: #EDF2F7
    width: 100%
    height: 100vh
    display: flex
    justify-content: center
    align-items: center
    position: relative

    img 
      position: absolute
      right: 50px
      bottom: 50px
</style>