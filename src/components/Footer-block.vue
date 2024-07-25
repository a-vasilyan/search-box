<template>
  <div class="footer-text">
    <div class="result">
      <p v-if="loading">searching...</p>
      <p v-else-if="count > 0">{{ count }} results</p>
      <p v-else-if="count < 1 && counter == 0">No result</p>
      <p v-else-if="count < 1 && counter" class="error-paragraph"> Something wrong happened but this is not your fault :)</p>

    </div>
  </div>
</template>

<script>
export default {
  
  props: {
        count: {
          type: Number,
          required: true,
        },
        counter: {
          type: Number,
          required: true,
        },
        loading: {
          type: Boolean,
          required: true,
        },
       
      },
}
</script>


<style lang="sass" scoped>
.footer-text
    position: absolute
    bottom: 0
    .result
        height: 51px
        gap: 10px
        border-radius: 0px 0px 20px 20px
        opacity: 0px
        display: flex
        align-items: center

        p
            font-family: Poppins
            font-size: 16px
            font-weight: 500
            line-height: 20px
            text-align: left
            color: #999FAA
        
        .error-paragraph 
          color: #ED2E7E
</style>