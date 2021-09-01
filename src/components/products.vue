<template >
  <div class="products">
    <productsItem
      v-bind:key="p.id"
      v-for="p of prod"
      v-bind:p="p"
      @remove="$emit('remove', p)"
    />
  </div>
</template>
<script>
import productsItem from "./products-item.vue";
export default {
  name: "products",
  components: { productsItem },
  props: ["prod"],
};
</script>
<style lang="scss">
.products {
  display: flex;
  flex-wrap: wrap;
  width: 100%;
  margin-left: 16px;
  margin-top: 80px;
}
</style>