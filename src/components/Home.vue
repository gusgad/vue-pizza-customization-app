<template>
  <main>
    <header>
      <h1>Vue Pizzeria</h1>
      <img src="../assets/italian-flag.png" alt="Italian flag">
    </header>
    
    <div class="container">

      <!-- PIZZA CARD -->
      <section>
        <img src="../assets/pizza-bacon.png" alt="Bacon-pizza image">
        <h3>{{ pizzaTitle }}</h3><button>schmakonize</button>
        <h4>{{ pizzaPrice }}€</h4>
        <p>{{ pizzaDescription }}</p>

        <div class="controls">
          <input type="text" name="ingredient" placeholder="Type an ingredient" v-model="ingredientInputValue">
          <button @click="addIngredient()">Add</button>
        </div>

        <div class="ingredients">
          <span v-for="ingredient in ingredients" :key="ingredient">{{ingredient}}</span>
        </div>
        
      </section>
      <!-- PIZZA CARD -->

    </div>

  </main>
</template>

<script>
import { ref } from 'vue'

export default {
  name: 'Home',
  setup() {
    // variables
    const pizzaTitle = ref('Bacon Pizza')
    const pizzaPrice = ref(8)
    const pizzaDescription = ref('Wonderfully flavored bacon pizza uses crisp bacon, vegetables, and sour cream for a special treat.')
    const ingredientInputValue = ref('')
    const ingredients = ref(['mozarella', 'basil'])

    // methods
    const addIngredient = () => {
      ingredients.value.push(ingredientInputValue.value)
    }

    return { pizzaTitle, pizzaPrice, pizzaDescription, ingredientInputValue, ingredients, addIngredient }
  }
}













/* data() {
  return {
    pizzaTitle: 'Bacon Pizza',
    pizzaPrice: 8,
    pizzaDescription: 'Wonderfully flavored bacon pizza uses crisp bacon, vegetables, and sour cream for a special treat.',
    ingredientInputValue: '',
    ingredients: ['mozarella', 'basil']
  }
},
methods: {
  addIngredient() {
    this.ingredients.push(this.ingredientInputValue);
  },
} */
</script>

<style scoped src="./Home.css"></style>