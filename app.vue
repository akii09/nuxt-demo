<script setup lang="ts">
enum Gender {
  GIRL = "Girl",
  BOY = "Boy",
  UNISEX = "Unisex",
}

enum Popularity {
  TRENDY = "Trendy",
  UNIQUE = "Unique",
}

enum Length {
  LONG = "Long",
  SHORT = "Short",
  ALL = "All",
}

interface OptionsState {
  gender: Gender;
  popularity: Popularity;
  length: Length;
}

const options = reactive<OptionsState>({
  gender: Gender.GIRL,
  popularity: Popularity.TRENDY,
  length: Length.ALL,
});

const names = ref<string[]>([]);

</script>

<template>
  <div class="container">
    <h1>Baby name genraetoru</h1>
    <p>Choose your options and clck the "Find Names" button below</p>
    <div class="options-container">
      <div class="option-container">
        <h4>1) Choose a gender</h4>
        <div class="option-btn">
          <button
            @click="options.gender = Gender.BOY"
            :class="options.gender === Gender.BOY && 'option-active'"
            class="option option-left"
          >
            Boy
          </button>
          <button
            @click="options.gender = Gender.UNISEX"
            :class="options.gender === Gender.UNISEX && 'option-active'"
            class="option"
          >
            Unisex
          </button>
          <button
            class="option option-right"
            :class="options.gender === Gender.GIRL && 'option-active'"
            @click="options.gender = Gender.GIRL"
          >
            Girl
          </button>
        </div>
      </div>
      <div class="option-container">
        <h4>2) Chose the name`s popularity</h4>
        <div class="option-btn">
          <button
            @click="options.popularity = Popularity.TRENDY"
            :class="options.popularity === Popularity.TRENDY && 'option-active'"
            class="option option-left"
          >
            Trendy
          </button>
          <button
            @click="options.popularity = Popularity.UNIQUE"
            :class="options.popularity === Popularity.UNIQUE && 'option-active'"
            class="option option-right"
          >
            Unique
          </button>
        </div>
      </div>
      <div class="option-container">
        <h4>3) Chose the name`s length</h4>
        <div class="option-btn">
          <button
            @click="options.length = Length.LONG"
            :class="options.length === Length.LONG && 'option-active'"
            class="option option-left"
          >
            Long
          </button>
          <button
            @click="options.length = Length.ALL"
            :class="options.length === Length.ALL && 'option-active'"
            class="option"
          >
            All
          </button>
          <button
            @click="options.length = Length.SHORT"
            :class="options.length === Length.SHORT && 'option-active'"
            class="option option-right"
          >
            Short
          </button>
        </div>
      </div>
      <button class="primary-btn">Find Name</button>
    </div>
  </div>
</template>

<style scoped>
.container {
  font-family: Arial, Helvetica, sans-serif;
  color: rgba(27, 60, 138);
  text-align: center;
  margin: 0 auto;
  max-width: 50rem;
}

h1 {
  font-size: 3rem;
}

.options-container {
  background-color: rgb(255, 238, 236);
  border-radius: 2rem;
  padding: 1rem;
  width: 95%;
  margin: 0 auto;
  margin-top: 4rem;
  position: relative;
}

.options-container {
  margin-bottom: 2rem;
}

.option {
  background-color: #fff;
  outline: 0.15rem solid rgb(249, 87, 89);
  border: none;
  padding: 0.75rem;
  widows: 12rem;
  font-size: 1rem;
  color: rgb(27, 60, 138);
  cursor: pointer;
  font-weight: 200;
}

.option-left {
  border-radius: 1rem 0 0 1rem;
}

.option-right {
  border-radius: 0 1rem 1rem 0;
}

.option-active {
  background-color: rgb(249, 87, 89);
  color: #fff;
}

.primary-btn {
  background-color: rgb(249, 87, 89);
  color: #fff;
  border: none;
  border-radius: 6.5rem;
  padding: 0.75rem 4rem; 
  font-size: 1rem;
  font-weight: 200;
  cursor: pointer;  
  margin-top: 2rem; 
}
</style>
