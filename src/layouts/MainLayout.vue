<template>
  <q-layout view="lHh Lpr lFf">
    <q-header
      elevated
      style="
        display: flex;
        justify-content: space-between;
        width: 100%;
        height: 90px;
        opcaity: 100%;
      "
    >
      <q-toolbar
        id="torn_edge_banner"
        class="torn_container torn_left torn_right"
      >
        <div></div>
        <div
          style="
            width: 100%;
            height: 90px;
            display: flex;
            justify-content: space-between;
          "
        >
          <q-toolbar-title class="banner_text" @click="clicked">
            Laser counter</q-toolbar-title
          >
          <q-btn-toggle
            class="banner_text"
            v-model="model"
            flat
            stretch
            toggle-color="white"
            :options="options"
            @click="reDir(model)"
          />
        </div>
      </q-toolbar>
    </q-header>

    <q-page-container>
      <router-view />
    </q-page-container>
  </q-layout>
</template>

<script>
export default {
  name: "MainLayout",
  data() {
    return {
      model: "",
      options: [
        { label: "In", value: "/InPage" },
        { label: "Out", value: "/OutPage" },
        { label: "Current", value: "/NetPage" },
      ],
    };
  },
  methods: {
    clicked() {
      this.$router.push("/");
    },
    reDir(page) {
      this.$router.push(page);
    },
  },
};
</script>

<style>
@import url("../pages/style.css");
</style>
