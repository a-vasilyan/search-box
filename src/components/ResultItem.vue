<template>
  <div class="item">
    <div class="item-img">
      <img :src="image" alt="" />
    </div>
    <div class="item-text">
      <h4>{{ title }}</h4>
      <p>{{ description }}</p>
    </div>
    <img :src="Vector" alt="" class="vector-svg" />
  </div>
</template>
  
  <script>
import Vector from "../assets/Icons/Vector.svg"; 
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    image: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      Vector: Vector, 
    };
  },
};
</script>
  
  <style lang="sass" scoped>
.item
    margin-top: 20px
    width: 587px
    height: 100px
    padding: 12px 20px 12px 12px
    gap: 20px
    border-radius: 12px
    display: flex
    background-color: transparent
    justify-content: center
    align-items: center
    transition: 0.3s

    &:hover
        background-color: #f2f4f8

        .vector-svg
            opacity: 1

    .item-text
        width: 468px
        height: 76px
        display: flex
        justify-content: center
        flex-direction: column
        gap: 8px

    h4
        font-family: Poppins
        font-size: 20px
        font-weight: 400
        line-height: 26px
        text-align: left

    p
        font-family: Poppins
        font-size: 16px
        font-weight: 400
        line-height: 20px
        letter-spacing: 0.75px
        text-align: left
        color: #999faa

    .vector-svg
        opacity: 0
    
    .item-img
        img
            width: 76px
</style>
  