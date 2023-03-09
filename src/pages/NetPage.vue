<template>
  <div style="display: flex; justify-content: center">
    <ShowCard :title="cur.title" :num="cur.num" />
  </div>
</template>

<script>
import ShowCard from "../components/ShowCard.vue";
export default {
  components: { ShowCard },
  data() {
    return {
      cur: { title: "NET", num: 3 },
    };
  },
};
</script>

<style></style>
