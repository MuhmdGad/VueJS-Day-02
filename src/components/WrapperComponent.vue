<template>
  <HeaderComponent />
  <div class="row">
    <LinksComponent />
    <DataTableComponent />
  </div>
  <FooterComponent />
</template>

<script>
import HeaderComponent from "./HeaderComponent.vue";
import LinksComponent from "./LinksComponent.vue";
import DataTableComponent from "./DataTableComponent.vue";
import FooterComponent from "./FooterComponent.vue";

export default {
  name: "wrapperComponent",

  components: {
    HeaderComponent,
    LinksComponent,
    DataTableComponent,
    FooterComponent,
  },
};
</script>
