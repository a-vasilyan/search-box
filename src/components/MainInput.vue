<template>
  <div class="search-box" :class="{ 'border-error': count < 1 && counter }">
    <img :src="SearchSvg" alt="" />
    <input
      type="text"
      v-model="inputValued"
      @input="handleInput"
      placeholder="Search what technologies we are using at DC..."
    />
  </div>
</template>

<script>
import SearchSvg from "../assets/Icons/SearchIcon.svg";
export default {
  data() {
    return {
      SearchSvg: SearchSvg,
      inputValued: this.category,
    };
  },
  props: {
    count: {
      type: Number,
      required: true,
    },
    counter: {
      type: Number,
      required: true,
    },
    inputValue: {
      type: String,
      required: true,
    },
    filteredData: {
      type: Array,
      required: true,
    },
    category: {
      type: String,
      required: true,
    },
  },
  watch: {
    category: {
      handler(newVal) {
        this.inputValued = newVal;
      },
      immediate: true, 
    },
  },
  methods: {
    handleInput() {
      const searchTerm = this.inputValued.trim().toLowerCase();
      if (searchTerm === "") {
        this.$emit("update-filtered-data", []); 
      } else {
        const filteredResults = this.filteredData.filter(item =>    
          item.title.toLowerCase().includes(searchTerm)
        );
          this.$emit("update-filtered-data", filteredResults); 
      }
    },
  },
};
</script>


<style lang="sass" scoped>
.search-box
    width: 601px
    height: 74px
    gap: 12px
    border-radius: 12px
    opacity: 0.8
    display: flex
    align-items: center
    background-color: #F2F4F8
    justify-content: center
    transition: border-color 0.3s ease

    &.border-error
        border: 2px solid #ED2E7E

    &:focus-within
        border: 3px solid #6833FF

    img
        width: 24px
        height: 24px
        gap: 0px
        opacity: 0.8
    input
        width: 471px
        height: 26px
        gap: 0px
        opacity: 0px
        border: none
        background-color: #F2F4F8
        outline: none
        font-size: 20px
        font-weight: 400
        line-height: 26px
        text-align: left
        
</style>
