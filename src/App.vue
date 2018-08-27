<template>
  <div id="app">
    <v-form
      :values="{ name: 'Sebastian' }"
      @submit="submit"
    >
      <v-field name="name">
        <template slot-scope="{ value, update }">
          <input
            :value="value"
            @input="update($event.target.value)"
          >
        </template>
      </v-field>
      <v-field name="name">
        <template slot-scope="{ value, update }">
          <input
            :value="value"
            @input="update($event.target.value)"
          >
        </template>
      </v-field>
      <button type="Submit">
        Submit
      </button>
    </v-form>
  </div>
</template>

<script>
import VForm from "./components/VForm";
import VField from "./components/VField";

export default {
  name: "app",

  components: {
    VForm,
    VField
  },

  methods: {
    submit(values) {
      console.log(values);
    }
  }
};
</script>
