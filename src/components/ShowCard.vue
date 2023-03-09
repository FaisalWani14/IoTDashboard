<template>
  <CardSlot>
    <template #card-header>
      <q-icon name="compare_arrows" size="4em" />
      <p>{{ title }}</p>
    </template>
    <template #card-content>
      <div class="tt">{{ num }}</div>
    </template>
  </CardSlot>
</template>

<script>
import CardSlot from "../components/CardSlot.vue";
export default {
  name: "ShowCard",
  components: { CardSlot },
  props: {
    num: { type: Number, required: true },
    title: { type: String, required: true },
  },
};
</script>
<style>
.tt {
  color: #000;
  font-size: 5em;
}
</style>
