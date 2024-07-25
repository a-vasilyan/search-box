<template>
    <div class="tag" @click="handleClick" :class="{ active: isActive }">
      <img :src="Icon" alt="" />
      <p>{{ tagText }}</p>
    </div>
  </template>
  
  <script>
  import Icon from "../assets/Icons/Icon.svg";
  
  export default {
    props: {
      tagText: {
        type: String,
        required: true,
      },
      onClick: {
        type: Function,
        required: true,
      },
    },
    data() {
      return {
        Icon: Icon,
        isActive: false, 
      };
    },
    methods: {
      handleClick() {
        this.isActive = !this.isActive; 
        this.onClick(); 
      },
    },
  };
  </script>
  
  <style lang="sass" scoped>
  .tag
    height: 32px
    gap: 10px
    display: flex
    align-items: center
    background-color: white
    border-radius: 40px
    padding: 7px 16px
    transition: background-color 0.3s ease
  
    &:hover
      cursor: pointer
      background-color: #865cff
      p
        color: white
      img
        filter: brightness(0) invert(1)
  
    p
      color: #6833ff
      font-family: Poppins
      font-size: 14px
      font-weight: 500
      line-height: 18px
      letter-spacing: 0.75px
      text-align: center
  
    &.active
      background-color: #6833FF
      
      p
        color: white
      img
        filter: brightness(0) invert(1)
  </style>
  