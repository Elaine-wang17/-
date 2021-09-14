<template>
  <div id="centerRight1">
    <div class="bg-color-black">
      <div class="d-flex pt-2 pl-2">
        <span style="color:#5cd9e8">
          <icon name="chart-line"></icon>
        </span>
        <div class="d-flex">
          <span class="fs-xl text mx-2">疫情快讯</span>
        </div>
      </div>
      <div class="d-flex jc-center body-box">
        <dv-scroll-board :config="config" style="width:3.375rem;height:4.0rem" />
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      config: {},
    };
  },
  components: {},
  mounted() {
    this.getNews();
    console.log("新闻");
  },
  methods: {
    async getNews() {
      const { data: res } = await this.$http.get("nCoV/api/news?page=1&num=10")
      let temp = res.results;
      let newsArr = [];
      for(let i=0;i<temp.length;i++) {
        newsArr.push([`<a style='color:white' href=${temp[i].sourceUrl}}}> ${temp[i].title} </a>`])
      }
      this.config = {
        header: ["新闻"],
        data: newsArr,
        rowNum: 7, //表格行数
        headerHeight: 35,
        headerBGC: "#0f1325", //表头
        oddRowBGC: "#0f1325", //奇数行
        evenRowBGC: "#171c33", //偶数行
        index: true,
        columnWidth: [50],
        align: ["center"]
      }
    }
  }
};
</script>

<style lang="scss">
#centerRight1 {
  padding: 0.2rem;
  height: 5.125rem;
  min-width: 3.75rem;
  border-radius: 0.0625rem;
  .bg-color-black {
    height: 4.8125rem;
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