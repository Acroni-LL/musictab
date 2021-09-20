
<script>
import Content from "./content.vue";

export default {
  name: "Tabs",
  data() {
    return {
      panes: [],
    };
  },
  props: {
    currentIndex: {
      type: [String, Number],
      default: "1",
    },
  },
  methods: {
    onChangeIndex(index) {
      // console.log(index);
      this.$emit("changeTab", index);
    },
  },
  components: {
    Content,
  },
  render() {
    return (
      <div>
        <ul class="tabs-header">{this.$slots.default}</ul>
        <Content panes={this.panes} />
      </div>
    );
  },
};
</script>

<style scoped>
.tabs-header {
  display: flex;
  list-style: none;
  margin: 0;
  padding: 0;
  border-bottom: 2px solid #ededed;
}
</style>