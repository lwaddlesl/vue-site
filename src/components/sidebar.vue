<template >
  <div class="sidebar">
    <div class="sidebar__tittle">Добавление товара</div>
    <div class="sidebar__forms">
      <form @submit.prevent="onSubmit">
        <div class="tittle">Наименнование товара</div>
        <textarea
          id="name"
          class="name"
          type="text"
          v-model="name"
          placeholder="Введите наименование товара"
        ></textarea>

        <div class="tittle-optional">Описание товара</div>
        <textarea
          class="discription"
          type="text"
          placeholder="Введите описание товара"
          v-model="discription"
        ></textarea>

        <div class="tittle">Ссылка на изображение товара</div>
        <textarea
          id="img"
          class="img"
          type="text"
          placeholder="Введите ссылку"
          v-model="img"
        ></textarea>

        <div class="tittle">Цена товара</div>
        <textarea
          id="price"
          class="price"
          type="text"
          placeholder="Введите цену"
          v-model="price"
        ></textarea>

        <button class="btn" type="submit">Добавить товар</button>
      </form>
    </div>
  </div>
</template>
<script>
export default {
  name: "sidebar",
  components: {},
  data() {
    return {
      name: "",
      discription: "",
      img: "",
      price: "",
    };
  },
  methods: {
    onSubmit() {
      if (this.name.trim() && this.img.trim() && this.price.trim()) {
        const product = {
          id: Date.now(),
          name: this.name,
          img: this.img,
          discription: this.discription,
          price: this.price,
        };
        this.$emit("add-product", product);
        this.name = "";
        this.discription = "";
        this.img = "";
        this.price = "";
      }
    },
  },
};
</script>
<style lang="scss">
.sidebar {
  margin-top: 32px;
  margin-left: 32px;
  .sidebar__tittle {
    font-weight: 600;
    font-size: 28px;
    color: #3f3f3f;
    margin-bottom: 20px;
  }
  .sidebar__forms {
    padding-top: 24px;
    padding-left: 24px;
    width: 332px;
    height: 440px;

    background: #fffefb;
    box-shadow: 0px 20px 30px rgba(0, 0, 0, 0.04),
      0px 6px 10px rgba(0, 0, 0, 0.02);
    border-radius: 4px;
    .tittle::after {
      content: "";
      position: absolute;
      width: 4px;
      height: 4px;
      background-color: red;
      border-radius: 4px;
    }
    textarea {
      margin-top: 4px;
      margin-bottom: 16px;
      width: 284px;
      height: 36px;
      padding-top: 10px;
      padding-left: 16px;
      box-shadow: 0px 2px 5px rgba(0, 0, 0, 0.1);
      border-radius: 4px;
      &:focus {
        box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.1);
      }
    }
    .discription {
      width: 284px;
      height: 108px;
    }
    .btn {
      background-color: rgb(14, 230, 14);
      width: 284px;
      height: 36px;
      border-radius: 10px;
      &:active {
        box-shadow: 0px 8px 10px rgba(0, 0, 0, 0.1);
        background-color: rgb(28, 180, 79);
      }
    }
  }
}
</style>