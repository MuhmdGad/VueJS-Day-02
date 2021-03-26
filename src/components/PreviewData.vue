<template>
  <div id="PreviewData">
    <h3 class="text-center" id="title"> Review Your Info Please</h3>
    <div class="row">
      <div class="col-4 text-right">Name</div>
      <div class="col-8 ">{{ data.name }}</div>
      <hr />
      <div class="col-4 text-right">Email</div>
      <div class="col-8 ">{{ data.email }}</div>
      <hr />

      <div class="col-4 text-right">Password</div>
      <div class="col-8 ">{{ data.password }}</div>
      <hr />

      <div class="col-4 text-right">Address</div>
      <div class="col-8 ">{{ data.address }}</div>
      <hr />

      <div class="col-4 text-right">Bio</div>
      <div class="col-8 pre">{{ data.bio }}</div>
      <hr />

      <div class="col-4 text-right">Gender</div>
      <div class="col-8 pre">{{ data.gender }}</div>
      <hr />

      <div class="col-4 text-right">Track</div>
      <div class="col-8 pre">{{ data.track }}</div>
      <hr />

      <div class="col-4 text-right">Languages</div>
      <div class="col-8 pre">
        <ul class="list-inline">
          <li class="list-inline-item mx-2 d-inline-block" v-for="lang in data.langs" >{{ lang }}</li>
        </ul>
      </div>
      <hr />
    </div>
  </div>
</template>

<script>
export default {
  name: "PreviewData",
  props: {
    data: {
      required: true,
      type: Object,
    },
  },
  data() {
    return {};
  },
};
</script>

<style scoped>
.pre {
  white-space: pre;
}
#PreviewData {
  padding: 50px;
  background: #042d57;
  background: #000910de;
  color:whitesmoke;
  border-radius: 12px;
}
h3 {
  margin-bottom: 35px;
  text-decoration: underline;
}
#title{
    text-align: left;
    color:#e9ecef;

}
</style>
