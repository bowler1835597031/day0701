<template>
  <div>
    <p>国内网站:粉丝数量:{{ msg | fans }}万</p>
    <p>国外网站:粉丝数量:{{ msg | fans(1) }}千</p>

    <p>{{ time | formatDate }}</p>
    <p>{{ time | formatDate(1) }}</p>
  </div>
</template>

<script>
import moment from 'moment';
export default {
  data() {
    return {
      msg: 1876986,
      time: new Date(),
    };
  },
  filters: {
    fans(val, a) {
      if (a) {
        return val / 10000;
      } else {
        return val / 1000;
      }
    },
    formatDate(val, b) {
      if (b) {
        return moment(val).format('YYYY/MM/DD');
      } else {
        return moment(val).format('YYYY-MM-DD');
      }
    },
  },
};
</script>

<style></style>
