<script setup>

// ref is used here to make an element reactive 
import { ref } from 'vue';

//Your JS logic goes here
// Using Composition API

// reactive state of the variable location 
const location = ref("London");
// Function to change location with the button click 
const changeLocation = () => {
      if(location.value === "London"){
        location.value = "New York"
      }  
      else {location.value = "Barcelona"}
  } 

//Creating a counter for cart 
const counter = ref(0)

const addToCart = () => {
  if(counter.value < 10)
      counter.value++;
    }
const removeFromCart = () => {
  if(counter.value > 0)
      counter.value--;
    }
    const isOpen = ref(true);
</script>

<template>
  <div>
<!--- Write your HTML here -->
  <h1>Daily Grind Cafe</h1> <br>
  <h2>Delicous Hot Coffee</h2>
<!-- Using V-IF and V-ELSE for conditinal rendering-->
  <p v-if="isOpen">We are Open! </p>
  <p v-else>We are Closed! </p>
  <!--  Text Interpolation -->
  <p class="location">Located @ {{ location }}</p> <br>
  <!-- Directives V-ON and V-BIND -->
<button v-on:click="changeLocation">Change Location</button><br>
<button v-on:click="addToCart" v-bind:disabled="counter === 10">Add To Cart</button>
<!-- Instead of v-on:click you can use @click /// :disabled is shorthand-->
<button @click="removeFromCart" :disabled="counter === 0">Remove To Cart</button><br>
<p> Cart: {{ counter }}</p>
</div>
</template>

<style scoped>
h2{
  color: brown;
}

.location{
  color: rgb(57, 158, 55);
}
</style>