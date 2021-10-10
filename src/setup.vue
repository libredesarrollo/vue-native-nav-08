<template>
  <view :style="{ minHeight: '100%' }">
    
    <view class="container">
      <app />
    </view>

    
  </view>
</template>

<script>
import App from "./index";

export default {
  components: {
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