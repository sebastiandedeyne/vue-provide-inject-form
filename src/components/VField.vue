<script>
export default {
  props: {
    name: { required: true }
  },

  inject: ["form"],

  render(h) {
    return h(
      "div",
      {},
      this.$scopedSlots.default({
        value: this.form.get(this.name),
        update: value => this.form.set(this.name, value)
      })
    );
  }
};
</script>
