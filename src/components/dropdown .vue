<template >
  <div class="dropdown">
    <select class="filter">
      <option value="s1" selected>По умолчанию</option>
      <option value="s1">max</option>
      <option value="s2">min</option>
      <option value="s3">name</option>
    </select>
  </div>
</template>
<script>
export default {
  name: "dropdown",
  components: {},
};
</script>
<style lang="scss">
.dropdown {
  margin-top: 30px;
  margin-right: 30px;

  .filter {
    width: 120px;
    height: 36px;
  }
}
</style>