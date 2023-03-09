<template>
  <CardSlot>
    <template #card-header> Student No. {{ id }}</template>
    <template #card-content> {{ name }} </template>
    <template #card-footer>
      <q-icon
        name="delete"
        color="primary"
        size="2em"
        @click="removeItem(id)"
      />
    </template>
  </CardSlot>
</template>

<script>
import CardSlot from "../components/CardSlot.vue";
export default {
  name: "DashCard",
  components: { CardSlot },
  props: {
    id: { type: Number, required: true },
    name: { type: String, required: true },
  },
  methods: {
    removeItem(id) {
      this.$emit("delete", id);
    },
  },
};
</script>

<style></style>
