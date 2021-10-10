<template>
  <view :style="{ minHeight: '100%' }">
    <drawer :navigation="navigation" ref="drawer" />
    <button title="Ir a Detalle" @press="goToDetail"></button>

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
    goToDetail() {
      this.navigation.navigate("Details");
    },
  },
};
</script>