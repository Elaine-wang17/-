<template>
  <div id="center">
    <div class="up">
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">全球累计确诊</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ globalList.confirmedCount }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">全球累计死亡</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ globalList.deadCount }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">全球单日新增</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ globalList.confirmedIncr }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">全球新增死亡</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ globalList.deadIncr }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">我国累计确诊</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ homeList.confirmedCount }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">我国累计死亡</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ homeList.deadCount }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">我国单日新增</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ homeList.confirmedIncr }}
        </div>
      </div>
      <div class="bg-color-black item" style="text-align: center">
        <p class="ml-3 colorBlue fw-b">我国新增死亡</p>
        <div style="font-size: 0.5rem; margin: 0.2rem auto">
          {{ homeList.deadIncr }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import CenterChart from "@/components/echart/center/centerChartRate";

export default {
  data() {
    return {
      homeList: [],
      globalList: {},
    };
  },
  mounted() {
    this.getBasicInfo();
    console.log("center")
  },
  methods: {
    async getBasicInfo() {
      const {
        data: { results: res },
      } = await this.$http.get("nCoV/api/overall");
      this.homeList = res[0];
      this.globalList = res[0].globalStatistics;
    },
  },
};
</script>

<style lang="scss" scoped>
#center {
  display: flex;
  flex-direction: column;
  .up {
    width: 100%;
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    .item {
      border-radius: 0.0625rem;
      padding-top: 0.2rem;
      margin-top: 0.1rem;
      width: 25%;
      height: 1.3rem;
    }
  }
  .down {
    padding: 0.07rem 0.05rem;
    padding-bottom: 0;
    width: 100%;
    display: flex;
    height: 3.1875rem;
    justify-content: space-between;
    .bg-color-black {
      border-radius: 0.0625rem;
    }
    .ranking {
      padding: 0.125rem;
      width: 59%;
    }
    .percent {
      width: 40%;
      display: flex;
      flex-wrap: wrap;
      .item {
        width: 50%;
        height: 1.5rem;
        span {
          margin-top: 0.0875rem;
          display: flex;
          justify-content: center;
        }
      }
      .water {
        width: 100%;
      }
    }
  }
}
</style>