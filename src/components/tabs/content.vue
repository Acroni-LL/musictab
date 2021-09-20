<template>
  <div>
    <!-- <div v-for="(item, index)in panes">{{ item }}</div> -->
  </div>
</template>

<script>
export default {
  name: "Content",
  props: {
    panes: {
      type: Array,
      default: function () {
        return [];
      },
    },
  },
  render() {
    return (
      <div>
        {this.panes.map((element, index) => {
          return element.active ? element.$slots.default : "";
        })}
      </div>
    );
  },
  mounted() {
    console.log(this.panes);
  },
};
</script>

<style>
</style>