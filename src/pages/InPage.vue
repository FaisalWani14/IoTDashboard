<template>
  <div style="display: flex; justify-content: center">
    <ShowCard :title="this.cur.title" :num="this.cur.num" />
  </div>
</template>

<script>
import ShowCard from "../components/ShowCard.vue";
export default {
  components: { ShowCard },
  data() {
    return {
      cur: { title: "IN", num: 5 },
    };
  },
};
</script>

<style></style>
