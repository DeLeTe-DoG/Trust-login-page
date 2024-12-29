<template>
  <div className="charts_section">
    <div className="chart_block" v-for="el in groups_stats_data" :key="el.id">
      <div className="chart_block_header">
        <div className="barChart_n_group">
          <img src="../../assets/images/barIcon.svg" className="widget">
          <h2 className="groupName">{{ el.group_Name }}</h2>
        </div>

        <div className="more_info_btn">
          <p className="more_info_p">Подробнее</p>
        </div>
      </div>
      <v-chart class="chart" :option="option" />
    </div>
  </div>
</template>
  
  <script>
  import { use } from "echarts/core";
  import { CanvasRenderer } from "echarts/renderers";
  import { LineChart, BarChart } from "echarts/charts";
  import { GridComponent, TooltipComponent } from "echarts/components";
  import VChart, { THEME_KEY } from "vue-echarts";
  import { ref, provide } from "vue";
  
  use([CanvasRenderer, BarChart, GridComponent, TooltipComponent]);
  
  let data = [550000, 680000, 450000, 380000, 500000, 300000, 120000];

  for (let i = 0; i < data.length; i++) {
    data[i] = {
      value: data[i],
      itemStyle: {
        borderRadius: 18,
        width: 45,
        color: '#BFD5F8'
      }
    }
  }

  export default {
    props: {
      groups_stats_data: {
        type: Array,
        required: true,
      },
    },
    name: "BarChart",
    components: {
      VChart,
    },
    setup() {
      provide(THEME_KEY, "light");
      const option = ref({
        xAxis: {
          data: ["10:00", "12:00", "14:00", "16:00", "18:00", "20:00", "22:00"],
        },
        yAxis: {
          type: "value",
        },
        series: [
          {
            data: data,
            type: "bar",
          },
        ],
      });

    //   for (let i = 0; i < option.series.data.length; i++) {
    //     option.series.data[i] = {
    //         value: data[i],
    //         itemStyle: {
    //             borderRadius: 18,
    //         }
    //     }
    //   }
  
      return { option };
    },
  };
  </script>

<style>
  .charts_section{
    display: grid;
    width: 92vw;
    grid-template-columns: 1fr 1fr;
    gap: 20px;
    padding: 30px 0 40px 0;
  }
    .chart_block{
        /* width: 700px; */
        height: 330px;
        background-color: #FAFAFA;
        border-radius: 18px;
        padding-bottom: 30px;
    }
    .chart_block_header, .barChart_n_group{
      display: flex;
      flex-direction: row;
      align-items: center;
    }
    .chart_block_header{
      justify-content: space-between;
      background-color: #fff;
      border-radius: 18px 18px 0 0;
      padding: 15px;
    }
    .barChart_n_group{
      gap: 10px;
    }
    .chart canvas{
        border-radius: 20px;
    }
    .groupName{
      color: #2E343B;
      font-size: 16px;
      font-weight: 700;
    }
    .more_info_btn{
      width: 120px;
      /* height: 30px; */
      padding: 10px 0 10px 15px;
      background: url('../../assets/images/VectorArrowBlue.svg') no-repeat right #FAFAFA;
      background-position-x: 115px;
      border-radius: 15px;
    }
</style>