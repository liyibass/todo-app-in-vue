<template>
  <div>
    <header class="header">
      <h1>TodoList</h1>
    </header>
  </div>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style lang="scss" scoped>
.header {
  background: #333;
  color: #fff;
  text-align: center;
  padding: 10px;

  a {
    color: #fff;
    padding-right: 5px;
  }
}
</style>
