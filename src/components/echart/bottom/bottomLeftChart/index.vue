<template>
  <div>
    <Chart :cdata="cdata" />
  </div>
</template>

<script>
import Chart from "./chart.vue";
export default {
  data() {
    return {
      cdata: [
        {
          name: "南海诸岛",
          value: 0,
          eventTotal: 100,
          specialImportant: 10,
          import: 10,
          compare: 10,
          common: 40,
          specail: 20,
        },
        {
          name: "北京",
          value: 16,
        },
        {
          name: "天津",
          value: 31,
        },
        {
          name: "上海",
          value: 116,
        },
        {
          name: "重庆",
          value: 1,
        },
        {
          name: "河北",
          value: 0,
        },
        {
          name: "河南",
          value: 39,
        },
        {
          name: "云南",
          value: 238,
        },
        {
          name: "辽宁",
          value: 9,
        },
        {
          name: "黑龙江",
          value: 4,
        },
        {
          name: "湖南",
          value: 60,
        },
        {
          name: "安徽",
          value: 0,
        },
        {
          name: "山东",
          value: 19,
        },
        {
          name: "新疆",
          value: 0,
        },
        {
          name: "江苏",
          value: 14,
        },
        {
          name: "浙江",
          value: 54,
        },
        {
          name: "江西",
          value: 0,
        },
        {
          name: "湖北",
          value: 31,
        },
        {
          name: "广西",
          value: 16,
        },
        {
          name: "甘肃",
          value: 0,
        },
        {
          name: "山西",
          value: 4,
        },
        {
          name: "内蒙古",
          value: 3,
        },
        {
          name: "陕西",
          value: 0,
        },
        {
          name: "吉林",
          value: 0,
        },
        {
          name: "福建",
          value: 30,
        },
        {
          name: "贵州",
          value: 0,
        },
        {
          name: "广东",
          value: 71,
        },
        {
          name: "青海",
          value: 0,
        },
        {
          name: "西藏",
          value: 0,
        },
        {
          name: "四川",
          value: 15,
        },
        {
          name: "宁夏",
          value: 0,
        },
        {
          name: "海南",
          value: 0,
        },
        {
          name: "台湾",
          value: 1482,
        },
        {
          name: "香港",
          value: 90,
        },
        {
          name: "澳门",
          value: 2,
        },
      ],
    };
  },
  components: {
    Chart,
  },
  mounted() {
    // this.setData();
  },
  methods: {
    // 根据自己的业务情况修改
    // setData () {
    //   for (let i = 0; i < this.cdata.barData.length -1; i++) {
    //     let rate = this.cdata.barData[i] / this.cdata.lineData[i];
    //     this.cdata.rateData.push(rate.toFixed(2));
    //   }
    // },
  },
};
</script>

<style lang="scss" scoped>
</style>