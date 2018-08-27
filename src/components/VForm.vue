<template>
  <form @submit.prevent="submit">
    <slot></slot>
  </form>
</template>

<script>
export default {
  props: {
    values: { required: true }
  },

  data() {
    return {
      form: {
        values: this.values
      }
    };
  },

  provide() {
    return {
      form: {
        get: this.get.bind(this),
        set: this.set.bind(this)
      }
    };
  },

  methods: {
    get(name) {
      return this.form.values[name];
    },

    set(name, value) {
      this.form.values[name] = value;
    },

    submit() {
      this.$emit("submit", this.form.values);
    }
  }
};
</script>
