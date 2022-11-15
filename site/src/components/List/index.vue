<template>
  <div class="flex">
    <div v-for="dish in dishes" :key="dish.id">
      <DishCard
        :id="dish.id"
        :dish="dish.dish"
        :components="dish.components"
        :ingredients="dish.ingredients"
        :time="dish.time"
        :compleated="dish.compleated"
        @remove-dish="removeDish"
      />
    </div>
  </div>
</template>

<script>
import DishCard from "@/components/Card";
export default {
  name: "DishList",
  props: ["dishes"],
  components: { DishCard },
  methods: {
    removeDish(id) {
      this.$emit("remove-dish", id);
    },
  },
};
</script>

<style>
.flex {
  display: flex;
  justify-content: space-around;
}
</style>
