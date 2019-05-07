<template>
  <div v-bind:id="randomId">
    <p>{{name}}</p>
    <p>{{randomId + 100}}</p>
    <p>{{animals[0]}}</p>
    <p>{{name.split('').reverse().join('')}}</p>
    <p>{{randomId%2===0 ? "Deljiv" : "Nije deljiv"}}</p>

    <div v-if="name==='Tijasna'">hello {{name}}</div>

    <div v-else>Hello someone</div>

    <!-- <button v-on:click="handleClick">Click me</button> -->
    <button @click="handleClick">Click me</button>

    <a :href="link">Google</a>

    <form @submit.prevent="handleSubmit">
      <button type="submit">Submit</button>
    </form>

    <div :class="{'red' : isRed}">I'm red</div>

    <ul>
      <li v-for="(color,index) in colors" :key="color">{{index+1}} {{color}}</li>
    </ul>

    <input type="text" v-model="name">

    <button @click="myFun">Greet</button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      name: "Tijana",
      randomId: Math.random(),
      animals: ["dog", "cat"],
      link: "https://www.google.com/",
      isRed: true,
      colors: ["green", "red", "blue"]
    };
  },
  methods: {
    handleClick() {
      console.log("CLICKED");
    },
    handleSubmit() {
      console.log("Submitted");
    },
    myFun() {
      alert(`Hello ${this.name}`);
      // alert("Hello" + this.name);
    }
  }
};
</script>

<style>
.red {
  background-color: red;
}
</style>
