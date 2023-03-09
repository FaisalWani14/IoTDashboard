<template>
  HELLO
  <div>
    <div style="display: flex; justify-content: space-between">
      <ShowCard title="IN" :num="InVal" />
      <ShowCard title="OUT" :num="OutVal" />
      <ShowCard title="Current" :num="NetVal" />
    </div>
  </div>
</template>

<script>
import ShowCard from "../components/ShowCard.vue";
import { onMounted } from "vue";
import { defineComponent } from "vue";
import * as mqtt from "mqtt/dist/mqtt";

let InVal = 0;
let OutVal = 0;
let NetVal = InVal - OutVal;

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
          const msg = message.toString();
          if (topic == "/project/laser/in") {
            this.InVal = parseInt(msg);
            console.log("IN: " + this.InVal);
          } else if (topic == "/project/laser/out") {
            this.OutVal = parseInt(msg);
            console.log("Out: " + this.OutVal);
          }
          this.NetVal = this.InVal - this.OutVal;
        });
      }
    });
  },
  data() {
    return {
      client: null,
      arr: [{ title: "IN" }, { title: "OUT" }, { title: "Current" }],
      InVal: 0,
      OutVal: 0,
      NetVal: 0,
    };
  },
};
</script>

<style>
@import url("./style.css");
</style>
