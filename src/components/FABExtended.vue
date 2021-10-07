<template>
  <touchable-opacity class="fab_extended_base fab_dowm" :on-press="callback">
    <text :style="{ color: '#FFF' }"> {{ label }} </text>
  </touchable-opacity>
</template>

<script>
export default {
  props: {
    label: {
      type: String,
      requerid: true,
    },
    callback: {
      type: Function,
      requerid: true,
    },
  },
};
</script>

<style scoped>
 .fab_extended_base {
        background-color: #70227E;
        padding-top: 8px;
        padding-bottom: 8px;
        padding-right: 10px;
        padding-left: 10px;
        border-radius: 25px
    }
    .fab_dowm {
        position:absolute;
        top: 80%;
        left:10px;
        z-index:101;
        elevation:101;
    }
</style>