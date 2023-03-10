<template>
  <div style="display: flex; justify-content: center">
    <ShowCard :title="arr[0].title" :num="arr[0].num" />
    <h2>{{ arr }}</h2>
  </div>
</template>

<script>
import ShowCard from "../components/ShowCard.vue";
import { arr } from "../pages/IndexPage.vue";

export default {
  components: { ShowCard },
  data() {
    return {
      arr,
    };
  },
  methods: {
    func() {
      console.log("HELLO");
    },
  },
};
</script>

<style>
h2 {
  color: black;
  font-size: 50px;
}
</style>
