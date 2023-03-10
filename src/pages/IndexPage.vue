<template>
  <p class="text-black text-h1">Faisal</p>
  <div>
    <div style="display: flex; justify-content: space-between">
      <ShowCard
        v-for="(item, key) in arr"
        :key="key"
        :title="item.title"
        :num="item.num"
        class="SCard"
        :data-descr="item.desc"
      />
    </div>
  </div>
</template>

<script>
import ShowCard from "../components/ShowCard.vue";
import { defineComponent } from "vue";
import * as mqtt from "mqtt/dist/mqtt";

var InVal = 0;
var OutVal = 0;
let NetVal = InVal - OutVal;

const arr = [
  { title: "IN", num: InVal, desc: "number of people enter" },
  { title: "OUT", num: OutVal, desc: "number of people leave" },
  {
    title: "Current",
    num: NetVal,
    desc: "current number of people",
  },
];

export { arr };

export default {
  components: { ShowCard },
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
          const num = parseInt(message.toString());
          if (topic == "/project/laser/in") {
            this.arr[0].num = num;
            InVal = num;
            console.log("IN: " + InVal, arr[0].num);
          } else if (topic == "/project/laser/out") {
            this.arr[1].num = num;
            OutVal = num;
            console.log("Out: " + OutVal, arr[1].num);
          }
          this.arr[2].num = InVal - OutVal;
          NetVal = InVal - OutVal;
        });
      }
    });
  },
  data() {
    return {
      client: null,
      arr: [
        { title: "IN", num: InVal, desc: "number of people enter" },
        { title: "OUT", num: OutVal, desc: "number of people leave" },
        {
          title: "Current",
          num: NetVal,
          desc: "current number of people",
        },
      ],
    };
  },
};
</script>

<style>
@import url("./style.css");
.SCard[data-descr] {
  position: relative;
}
.SCard[data-descr]:hover::after,
.SCard[data-descr]:focus::after {
  content: attr(data-descr);
  position: absolute;
  left: 0;
  top: 54px;
  min-width: 200px;
  border: 1px #aaaaaa solid;
  border-radius: 10px;
  background-color: #ffffcc;
  padding: 12px;
  color: #000000;
  font-size: 14px;
  z-index: 1;
}
</style>
