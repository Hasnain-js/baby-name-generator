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
          @click="option.gender = Gender.BOY"
          >
            boy
          </button>
          <button class="option"
          :class="option.gender === 'unisex' && 'option-active'"
          @click="option.gender = Gender.UNISEX"
          >
            unisex
          </button>
          <button class="option option-right"
          :class="option.gender === 'girl' && 'option-active'"
          @click="option.gender = Gender.GIRL"
          >girl</button>
        </div>
    </div>
      <div class="option-container">
        <h4>2) Choose the name popularity</h4>
        <div class="option-buttons">
          <button class="option option-left"
          :class="option.popularity === 'trendy' && 'option-active'"
          @click="option.popularity = Popularity.TRENDY"
          >
            trendy
          </button>
          <button class="option option-right"
          :class="option.popularity === 'unique' && 'option-active'"
          @click="option.popularity = Popularity.UNIQUE"
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
          @click="option.length = Length.LONG"
          >long</button>
          <button class="option"
          :class="option.length === 'all' && 'option-active'"
          @click="option.length = Length.All"
          >all</button>
          <button class="option option-right"
          :class="option.length === 'short' && 'option-active'"
          @click="option.length = Length.SHORT"
          >short</button>
        </div>
    </div>
    <div class="option-container">
    </div>
    <button class="primary">Find Name</button>
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
    .options-container .primary{
      background: rgb(233, 66, 66);
      color:white;
      border-radius: 1rem;
      outline: none;
      border: none;
      padding: 0.75rem 4rem;
      font-size: 1rem;
      margin-top: 1rem;
      cursor: pointer;

    }
</style>
