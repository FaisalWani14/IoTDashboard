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
          <q-toolbar-title class="banner_text" @onClick="clicked()">
            Laser counter</q-toolbar-title
          >
          <q-btn-toggle
            class="banner_text"
            v-model="model"
            flat
            stretch
            toggle-color="white"
            :options="options"
            @click="reDir(options.link)"
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
      selected: "",
      in: 0,
      out: 0,
      net: 0,
      options: [
        { label: "In", value: "one", link: "/InPage" },
        { label: "Out", value: "two", link: "/OutPage" },
        { label: "Current", value: "three", link: "/NetPage" },
      ],
    };
  },
  methods: {
    clicked() {
      this.$router.push("/t");
    },
    reDir(page) {
      console.log(page);
    },
  },
};
</script>

<style>
@import url("../pages/style.css");
</style>
