<template>
  <div id="app">
    <tabs :currentIndex="currentIndex" @changeTab="changeTabHandler">
      <tab tabName="tab1" index="1"></tab>
      <tab tabName="tab2" index="2"></tab>
      <tab tabName="tab3" index="3"></tab>
    </tabs>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      currentIndex: "1",
    };
  },
  components: {},
  methods: {
    changeTabHandler(index) {
      this.currentIndex = index;
    },
  },
};
</script>

<style>
</style>
