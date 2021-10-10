<template>
  <view :style="{ minHeight: '100%' }">
    <drawer :navigation="navigation" ref="drawer" />
    <text> Hola Mundo Detalle </text>

    <button title="Ir a Home" @press="goToHome"></button>
    <button title="Back" @press="goBack()"></button>

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
import Drawer from "../components/DrawerComponent.vue";
import FABExtended from "../components/FABExtended.vue";
export default {
  components: {
    Drawer,
    FABExtended,
  },
  props: {
    navigation: {
      Object,
    },
  },
  methods: {
    goToHome() {
      this.navigation.navigate("Home");
    },
    goBack() {
      this.navigation.goBack();
    },
  },
};
</script>