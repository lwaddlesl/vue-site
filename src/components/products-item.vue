<template >
  <div class="products-item">
    <button class="delete" @click="$emit('remove', p)" />
    <img :src="p.img" alt="img" />
    <div class="product__name">{{ p.name }}</div>
    <div class="product__discroption">
      {{ p.discription }}
    </div>
    <div class="product__price">{{ p.price }}</div>
  </div>
</template>
<script>
export default {
  name: "products-item",
  components: {},
  props: {
    p: {
      type: Object,
      required: true,
    },
  },
};
</script>
<style lang="scss">
.products-item {
  position: relative;
  .delete {
    content: url("../assets/images/delete.png");
    opacity: -1;
    position: absolute;
    right: -8px;
    top: -8px;
    width: 32px;
    height: 32px;
    background: #ff8484;
    box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
    border-radius: 10px;
  }
  &:hover {
    .delete {
      opacity: 1;
    }
  }

  margin-left: 16px;
  margin-bottom: 16px;
  width: 332px;
  min-height: 423px;
  background: #fffefb;
  box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
    0px 6px 10px rgba(0, 0, 0, 0.02);
  border-radius: 4px;
  img {
    width: 332px;
  }
  .product__name {
    font-size: 20px;
    font-weight: 600;
    padding: 16px;
  }
  .product__discroption {
    padding: 16px;
    font-size: 16px;
  }
  .product__price {
    font-size: 24px;
    font-weight: 600;
    padding: 16px;
  }
}
</style>