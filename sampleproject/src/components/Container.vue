<template>
  <div id="container">
    <LPMain msg="List&Picture" />
  </div>
</template>

<script>
import LPMain from "./List&Picture/LPMain.vue";

export default {
  name: "Container",
  components: {
    LPMain,
  },
};
</script>

<style lang="scss" scoped>
#container {
  display: flex;
  justify-content: center;
  align-items: flex-start;
  background-color: rgba(235, 232, 232, 0.35);
  border: 1px solid rgba(235, 232, 232, 1);
  width: 98vw;
  min-height: calc(98vh - 256px);
}
@media (max-width: 640px) {
  #container {
    min-height: calc(98vh - 112px);
  }
}
</style>
