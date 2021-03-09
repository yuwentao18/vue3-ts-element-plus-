<template>
  <div class="about">
    <div class="grid">啊啊啊啊啊啊啊啊</div>
  </div>
</template>
<style lang="scss" scoped>
.about {
  width: 300px;
  height: 300px;
  .grid {
    display: grid;
    grid-template-columns: 100px 100px 100px;
    grid-template-rows: 100px 100px 100px;
    grid-template-areas:
      "a b c"
      "d e f"
      "g h i";
  }
}
</style>
