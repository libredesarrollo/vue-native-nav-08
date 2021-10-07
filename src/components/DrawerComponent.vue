<template>
  <animated:view
    class="drawer"
    :style="{
      transform: [{ translateX: translateX }],
    }"
  >
    <touchable-opacity
      :on-press="
        () => {
          navigation.navigate('Home');
        }
      "
    >
      <drawer-item title="Home" />
    </touchable-opacity>

    <drawer-item title="Detail" />
  </animated:view>
</template>

<script>
import { Animated, Easing } from "react-native";
import DrawerItem from "./DrawerItemComponent.vue";
export default {
  props: {
    navigation: {
      Object,
    },
  },
  components: { DrawerItem },
  data() {
    return {
      translateX: 0,
      translateXInter: 0,
      activate: false,
    };
  },
  created() {
    //this.translateX = new Animated.Value(0)
    this.translateXInter = new Animated.Value(0);
    this.translateX = this.translateXInter.interpolate({
      inputRange: [0, 1],
      outputRange: [0, -200],
    });
    //this.translateMenu()
  },
  methods: {
    translateMenu: function () {
      Animated.timing(this.translateXInter, {
        toValue: this.activate ? 0 : 1,
        duration: 500,
        easing: Easing.linear,
        useNativeDriver: true,
      }).start(() => {
        this.activate = !this.activate;
        this.translateXInter.setValue(this.activate ? 1 : 0);
        //  this.translateMenu();
      });
    },
  },
};
</script>

<style scoped>
.drawer {
  background-color: #fff;
  width: 200px;
  height: 100%;
  position: absolute;
  z-index: 100;
  elevation: 100;
  padding-top: 30px;
}
</style>