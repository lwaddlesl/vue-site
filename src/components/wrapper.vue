<template >
  <div class="wrapper">
    <sidebar @add-product="addProduct" />
    <products v-bind:prod="prod" @remove="removeProduct" />
    <dropdown />
  </div>
</template>
<script>
import sidebar from "./sidebar.vue";
import products from "./products.vue";
import Dropdown from "./dropdown .vue";
export default {
  name: "wrapper",
  components: {
    sidebar,
    products,
    Dropdown,
  },
  data() {
    return {
      prod: [
        {
          id: 1,
          img: "https://lh3.googleusercontent.com/proxy/OBjGsLoj45vuxVsTCvny0QCabdjuZaZv6GosR34_f1o3ZgrBeGY1gAGZdDvAu9_gH17TyiuWjVWT_jcQ7KBYZFERY28joTkJk5g7kU-9Ak422067uBp4FeJ-",
          name: "Наименование товара",
          discription:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
        },
        {
          id: 2,
          img: "https://lh3.googleusercontent.com/proxy/OBjGsLoj45vuxVsTCvny0QCabdjuZaZv6GosR34_f1o3ZgrBeGY1gAGZdDvAu9_gH17TyiuWjVWT_jcQ7KBYZFERY28joTkJk5g7kU-9Ak422067uBp4FeJ-",
          name: "Наименование товара",
          discription:
            "Довольно-таки интересное описание товара в несколько строк. Довольно-таки интересное описание товара в несколько строк",
          price: "10 000 руб.",
        },
      ],
    };
  },
  methods: {
    addProduct(product) {
      this.prod.push(product);
    },
    removeProduct(p) {
      this.prod = this.prod.filter((t) => t.id !== p.id);
    },
  },
};
</script>
<style lang="scss">
.wrapper {
  display: flex;
  width: 100%;
}
</style>