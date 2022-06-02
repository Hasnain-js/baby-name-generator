<script setup lang="ts">
enum Gender {
  BOY= "boy",
  GIRL = "girl",
  UNISEX = "unisex"
}
enum Length {
  SHORT = "short",
  LONG = "long",
  All = "all"
}
enum Popularity {
  TRENDY = "trendy",
  UNIQUE = "unique"
}
interface optionState {
  gender: Gender;
  popularity: Popularity;
  length: Length;
}
const option = reactive<optionState>({
  gender: Gender.BOY,
  length: Length.All,
  popularity: Popularity.TRENDY,
})
</script>
<template>
  <div class="container">
    <h1> Baby Name Generator</h1>
    <p>Choose your option and click the "Find name" button below</p>
    <div class="options-container">
        <div class="option-container">
        <h4>1) Choose a gender</h4>
        <div class="option-buttons">
          <button class="option option-left"
          :class="option.gender === 'boy' && 'option-active'"
          >
            boy
          </button>
          <button class="option"
          :class="option.gender === 'unisex' && 'option-active'"
          >
            unisex
          </button>
          <button class="option option-right"
          :class="option.gender === 'girl' && 'option-active'"
          >girl</button>
        </div>
    </div>
      <div class="option-container">
        <h4>2) Choose the name popularity</h4>
        <div class="option-buttons">
          <button class="option option-left"
          :class="option.popularity === 'trendy' && 'option-active'"
          >
            trendy
          </button>
          <button class="option option-right"
          :class="option.popularity === 'unique' && 'option-active'"
          >
            unique
          </button>
        </div>
    </div>
      <div class="option-container">
        <h4>3) Choose a name's length</h4>
        <div class="option-buttons">
          <button class="option option-left"
          :class="option.length === 'long' && 'option-active'"
          >long</button>
          <button class="option"
          :class="option.length === 'all' && 'option-active'"
          >all</button>
          <button class="option option-right"
          :class="option.length === 'short' && 'option-active'"
          >short</button>
        </div>
    </div>
    <div class="option-container">
    </div>
    </div>
  </div>
</template>



<style scoped>
    .container {
     color: rgb(27, 60, 138);
    font-family: sans-serif;
     max-width: 50rem;
     margin: 0 auto;
     text-align: center;
    }
    .container h1{
      font-size: 2.5rem;
    }
    .container p{
      font-size: 1.5rem;
      color: gray;
    }
    .options-container{
      background-color: rgb(255, 238, 236);
      border-radius: 2rem;
      padding: 1rem;
      margin: 0 auto;
      width: 90%;
      position: relative;
      margin-top: 4rem;
    }
    .option-container{
      margin-bottom: 2rem;
    }
    .option{
      background: white;
      outline: 0.15rem solid rgb(233, 66, 66);
      border: none;
      padding: 0.75rem;
      width: 12rem;
      font-size: 1.5rem;
      color: rgb(27, 60, 138);
      cursor: pointer;
    }
    .option-left{
      border-radius: 1rem 0 0 1rem;
    }
    .option-right{
      border-radius: 0 1rem 1rem 0;
    }
    .option-active{
      background: rgb(233, 66, 66);
      color: white;
    }
</style>
