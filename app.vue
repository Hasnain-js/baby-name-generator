<template>
  <div class="container">
    <h1> Baby Name Generator</h1>
    <p>Choose your option and click the "Find name" button below</p>
    <div class="option-container">
        <h4>1) Choose a gender</h4>
        <div class="option-buttons">
          <button class="option option-left">boy</button>
          <button class="option">unisex</button>
          <button class="option option-right">girl</button>
        </div>
    </div>
      <div class="option-container">
        <h4>2) Choose the name popularity</h4>
        <div class="option-buttons">
          <button class="option option-left">trendy</button>
          <button class="option option-right">unique</button>
        </div>
    </div>
      <div class="option-container">
        <h4>3) Choose a name's length</h4>
        <div class="option-buttons">
          <button class="option option-left">long</button>
          <button class="option">all</button>
          <button class="option option-right">short</button>
        </div>
    </div>
    <div class="option-container">
    </div>
  </div>
</template>



<style scoped>
    .container {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      margin: 0 auto;
    }
</style>
