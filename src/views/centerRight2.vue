<template>
  <div id="centerRight2">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span style="color:#5cd9e8">
          <icon name="align-left"></icon>
        </span>
        <span class="fs-xl text mx-2">全国现有确诊数排行</span>
      </div>
      <div class="d-flex jc-center body-box" style=" margin-top: 0;">
        <dv-capsule-chart :config="config" style="width: 100%;height:4rem" />
        <!-- ---------------------------------------- -->
        <!-- <centerRight2Chart1 /> -->
      </div>
    </div>
  </div>
</template>

<script>
//import centerRight2Chart1 from "@/components/echart/centerRight/centerRightChart";

export default {
  data() {
    return {
      config: {
        data: [
          {
            name: "台湾",
            value: 1482
          },
          {
            name: "云南",
            value: 243
          },
          {
            name: "上海",
            value: 118
          },
          {
            name: "香港",
            value: 88
          },
          {
            name: "广东",
            value: 72
          },
          {
            name: "湖南",
            value: 62
          },
          {
            name: "浙江",
            value: 54
          },
          {
            name: "河南",
            value: 48
          },
          {
            name: "湖北",
            value: 34
          },
          {
            name: "天津",
            value: 33
          }
        ]
      }
    };
  },
  // components: { centerRight2Chart1 },
  mounted() {},
  methods: {}
};
</script>

<style lang="scss">
#centerRight2 {
  padding: 0.0625rem;
  height: 5rem;
  min-width: 3.75rem;
  border-radius: 0.0625rem;
  .bg-color-black {
    padding: 0.0625rem;
    height: 5.0625rem;
    border-radius: 0.125rem;
  }
  .text {
    color: #c3cbde;
  }
  .body-box {
    border-radius: 0.125rem;
    overflow: hidden;
  }
}
</style>