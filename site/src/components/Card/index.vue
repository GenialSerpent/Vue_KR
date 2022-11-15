<template>
  <div class="border">
    <h2>{{ dish }}<button @click="$emit('remove-dish', id)">x</button></h2>
    <h4>Час приготування: {{ time }}хв.</h4>
    <p>{{ components }} складових:</p>
    <p v-for="(ingredient, index) in ingredients" :key="index">
      {{ index + 1 }}. {{ ingredient }}
    </p>
  </div>
</template>

<script>
export default {
  name: "DishCard",
  props: {
    id: Number,
    dish: String,
    components: Number,
    ingredients: Array,
    time: Number,
    compleated: Boolean,
  },
};
</script>

<style>
.border {
  border: 1px solid rgba(70, 73, 74, 0.831);
  padding: 20px 20px 20px 20px;
}
</style>
