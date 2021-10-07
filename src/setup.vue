<template>
  <view :style="{ minHeight: '100%' }">
    <drawer ref="drawer" />
    <view class="container">
      <app />
    </view>

    <FABExtended
      label="Menu"
      :callback="
        () => {
          this.$refs.drawer.translateMenu();
        }
      "
    />
  </view>
</template>

<script>
import App from "./index";
import Drawer from "./components/DrawerComponent.vue";
import FABExtended from "./components/FABExtended.vue";
export default {
  components: {
    Drawer,
    FABExtended,
    App,
  },
};
</script>

<style scoped>
.container {
  flex: 1;
  width: 90%;
  margin-top: 15px;
  margin-right: auto;
  margin-left: auto;
}
</style>