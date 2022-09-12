<template>
  <router-link :to="{ name: 'Home' }" class="back-btn">
    <h1 class="selectable" title="Back to Projects">🔙</h1>
  </router-link>
  <section class="row">
    <div class="col-md-4">
      <h3 class="text-center">Past</h3>
    </div>
    <div class="col-md-4">
      <h3 class="text-center">Present</h3>
    </div>
    <div class="col-md-4">
      <h3 class="text-center">Future</h3>
    </div>
  </section>
</template>


<script>
export default {
  setup() {
    return {}
  }
}
</script>


<style lang="scss" scoped>
.back-btn {
  position: absolute;
  top: 13px;
  left: 7px;
}
</style>
