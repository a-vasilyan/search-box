<template>
  <div class="search-block">
    <MainInput
      :count="filteredData.length"
      :category="category"
      :counter="counter"
      :inputValue="inputValue"
      :filteredData="searchData"
      @update-filtered-data="updateFilteredData"
    ></MainInput>
    <div class="tags-block">
      <TagButton
        tag-text="Languages"
        :onClick="() => filterByCategory('Languages & Frameworks')"
      />
      <TagButton tag-text="Build" :onClick="() => filterByCategory('Build')" />
      <TagButton
        tag-text="Design"
        :onClick="() => filterByCategory('Design')"
      />
      <TagButton tag-text="Cloud" :onClick="() => filterByCategory('Cloud')" />
    </div>
    <div v-if="!filteredData.length && change" class="search-img">
      <img v-if="counter === 0" :src="searching" alt="" />
      <img
      v-if="filteredData.length < 1 && counter > 0 "
      :src="errorImage"
      alt=""
      />
    </div>
    <div class="main-item-block">
      <div class="main-loader-block" v-if="loading ">
        <div class="loader"></div>
      </div>
      <div class="main-item-box" >
        <div v-if="!loading">

          <ResultItem 
            v-for="(item, index) in filteredData"
            :key="index"
            :title="item.title"
            :description="item.description"
            :image="item.image"
          />
        </div>
      </div>
    </div>
    <Footer :loading="loading" :count="filteredData.length" :counter="counter"></Footer>
  </div>
</template>

<script>
import MainInput from "./MainInput.vue";
import TagButton from "./TagButton.vue";
import searchingImage from "../assets/Images/searching.png";
import errorImage from "../assets/Images/error.png";
import Footer from "../components/Footer-block.vue";
import ResultItem from "./ResultItem.vue";

export default {
  components: {
    MainInput,
    TagButton,
    Footer,
    ResultItem,
  },
  data() {
    return {
      searching: searchingImage,
      errorImage: errorImage,
      counter: 0,
      inputValue: "",
      searchData: [],
      category: "",
      filteredData: [],
      change: true,
      loading: false,
    };
  },
  created() {
    this.fetchData();
  },
  methods: {
    async fetchData() {
      try {
       
          const response = await fetch(
            "https://frontend-test-api.digitalcreative.cn/?no-throttling=true&search=flutter"
          );
          const data = await response.json();
          this.searchData = data;
      } catch (error) {
        this.loading = false; 
      }
    },
    filterByCategory(category) {
      this.category = category
      this.change = false
      this.loading = true; 
        setTimeout(async () => {
          this.change = true
          this.loading = false;
        }, 1000);
      this.counter++;

      this.filteredData = this.searchData.filter((item) => {
        return item.category === category;
      });

      this.inputValue = category;
      this.resetActiveState(category.split(" ")[0]);
    },
    resetActiveState(categoryClicked) {
      this.inputValue = categoryClicked;
      this.$children.forEach((child) => {
        if (child.tagText !== categoryClicked) {
          child.isActive = false;
        }
      });
    },
    updateFilteredData(filteredData) {
      this.filteredData = filteredData;
      this.counter++;
      this.change = false
      this.loading = true; 
        setTimeout(async () => {
          this.change = true
          this.loading = false; 
        }, 1000);
    },
  },
};
</script>

<style lang="sass" scoped>
.search-block
  width: 650px
  max-height: 651px
  background-color: white
  padding: 24px
  border-radius: 20px
  position: relative

  .main-item-block
    min-height: 100px
    max-height: 450px
    overflow: auto
    position: relative

    .main-loader-block
      width: 100%
      height: 100%
      background-color: rgb(195 195 195 / 10%)
      position: absolute

      .loader
        width: 40px
        height: 40px
        background-image: url('../assets/Images/Loader.png')
        background-size: cover
        animation: spin 2s linear infinite
        top: 45%
        left: 45%
        position: absolute

        @keyframes spin
          0%
            transform: rotate(0deg)

          100%
            transform: rotate(360deg)
    .main-item-box
      padding-bottom: 15px

  .main-item-block::-webkit-scrollbar
    width: 10px
    height: 25px

  .main-item-block::-webkit-scrollbar-thumb
    background-color: gray
    border-radius: 8px
    height: 25px


  .tags-block
    display: flex
    gap: 16px
    padding-top: 20px

  .search-img
    padding: 111px 197.5px
</style>
