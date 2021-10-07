<template>
  <view class="item">
    <text>{{ title }}</text>
  </view>
</template>
<script>
export default {
  props: {
    title: {
      type: String,
      required: true,
    },
  },
};
</script>
<style scoped>
.item {
  border-color: gray;
  border-bottom-width: 1px;
  margin-top: 15px;
  margin-left: 15px;
  margin-right: 15px;
  padding-bottom: 10px;
}
</style>