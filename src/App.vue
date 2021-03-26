<template>
  <div id="app">
    <div class="container">
      <PreviewData v-if="preview" :data="form" />

      <RegisterForm v-else :data="form" @changeFormStatus="changeFormStatus" />

      <div class="d-flex justify-content-between my-4">
        <button v-if="preview" class="btn btn-primary" @click="preview = false">
          Edit
        </button>
        <button v-else  class="btn btn-primary" @click="preview = true" :disabled="invalid">Preview</button>
      </div>
    </div>
  </div>
</template>

<script>
import RegisterForm from "./components/RegisterForm.vue";
import PreviewData from "@/components/PreviewData";

export default {
  name: "App",
  components: {
    PreviewData,
    RegisterForm,
  },
  data() {
    return {
      invalid: true,
      preview: false,
      form: {
        name: "",
        langs: [],
      },
    };
  },
  methods: {
    changeFormStatus(status) {
      this.invalid = status;
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 40px;
}
button {
  display: block;
  width: 80%;
  margin: auto;
}
</style>
