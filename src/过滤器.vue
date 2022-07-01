<template>
  <div>
    <h1>{{ msg | toDown }}</h1>
    <h2 v-bind:title="msg | toUp">{{ msg | toUp | toReverse }}</h2>
  </div>
</template>

<script>
export default {
  filters: {
    // 过滤器名称(val) {
    //   return 处理后的数据;
    // },
    toUp(val) {
      console.log(val);
      return val.toUpperCase();
    },
  },
  data() {
    return {
      msg: 'hello world',
    };
  },
};
</script>

<style></style>
