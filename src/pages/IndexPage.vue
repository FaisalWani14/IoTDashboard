<template>
  <p class="text-black text-h1">yasu</p>
  <div>
    <div style="display: flex; justify-content: space-between">
      <ShowCard title="IN" :num="visitor.InVal" />
      <ShowCard title="OUT" :num="visitor.OutVal" />
      <ShowCard title="Current" :num="visitor.NetVal" />
    </div>
    <div class="chart-wrapper">
      <ApexChart
        width="800"
        type="area"
        :options="CurrentChart.options"
        :series="CurrentChart.series"
      />
    </div>
  </div>
</template>

<script>
import ShowCard from "../components/ShowCard.vue";
import { defineComponent } from "vue";
import * as mqtt from "mqtt/dist/mqtt";
import ApexChart from "vue3-apexcharts";

export default defineComponent({
  name: "IndexPage",
  components: {
    ShowCard,
    ApexChart,
  },
  created() {
    const clientId = "mqttjs_" + Math.random().toString(8);
    const host = "ws://broker.hivemq.com:8000/mqtt";
    const options = {
      keepalive: 30,
      clientId: clientId,
    };
    console.log("connecting mqtt client");
    this.client = mqtt.connect(host, options);
    this.client.subscribe("/project/laser/+", (err) => {
      if (!err) {
        this.client.on("message", (topic, message) => {
          const msg = message.toString();
          if (topic == "/project/laser/in") {
            this.visitor.InVal = parseInt(msg);
            console.log("IN: " + this.visitor.InVal);
          } else if (topic == "/project/laser/out") {
            this.visitor.OutVal = parseInt(msg);
            console.log("Out: " + this.visitor.OutVal);
          }
          this.visitor.NetVal = this.visitor.InVal - this.visitor.OutVal;
        });
      }
    });
    setInterval(() => {
      this.CurrentChart.options.xaxis.categories.push(Date.now());
      this.CurrentChart.options.xaxis.categories =
        this.CurrentChart.options.xaxis.categories.slice(-24);
      this.CurrentChart.series[0].data.push(this.visitor.InVal);
      this.CurrentChart.series[0].data =
        this.CurrentChart.series[0].data.slice(-24);
    }, 20000);
  },
  data() {
    return {
      client: null,
      visitor: {
        InVal: 0,
        OutVal: 0,
        NetVal: 0,
      },
      CurrentChart: {
        options: {
          chart: {
            id: "current",
          },
          xaxis: {
            categories: [],
          },
          colors: ["#26a69a"],
        },
        series: [
          {
            name: "time",
            data: [],
          },
        ],
      },
    };
  },
});
</script>

<style scoped>
@import url("./style.css");
div.chart-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
}
</style>
