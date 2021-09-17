
<script>
export default {
  name: "Tab",
  props: {
    index: {
      type: [String, Number],
      default: "1",
    },
    tabName: {
      type: String,
      default: "tab",
    },
  },
  computed: {
    active() {
      return this.$parent.currentIndex == this.index;
    },
  },
  methods: {
    changeIndexHandler() {
      // this.$emit("onChangeIndex", this.index);
      this.$parent.onChangeIndex(this.index);
      // console.log(this.index);
    },
  },
  mounted() {
    // this.$parent.panes.push(this.$slots.default);
    console.log(this.$parent.data());
  },
  render() {
    let className = {
      tab: "tab",
      active: this.active,
    };
    return (
      <li onClick={this.changeIndexHandler.bind(this)} class={className}>
        {this.tabName}
      </li>
    );
  },
};
</script>

<style scoped>
.tab {
  flex: 1;
  list-style: none;
  line-height: 40px;
  margin-right: 30px;
  position: relative;
  text-align: center;
}
.tab.active {
  border-bottom: 2px solid blue;
}
</style>