<template>
  <div class="dashboard-card">
    <div class="dashboard-card__image-containern">
      <img :src="getImgUrl(image)" alt />
    </div>
    <div>
      <h6>{{heading}}</h6>
      <div>{{subHeading}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: "DashboardCard",
  props: ["heading", "subHeading", "image"],
  methods: {
    getImgUrl(pic) {
      return require("../../assets/icons/" + pic);
    },
  },
};
</script>
