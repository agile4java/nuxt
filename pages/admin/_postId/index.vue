<template>
  <div class="admin-post-page">
    <section class="update-form">
      <AdminPostForm :post="loadedPost"/>
    </section>
  </div>
</template>
<script>
import AdminPostForm from "@/components/Admin/AdminPostForm";

export default {
  components: {
    AdminPostForm
  },
  data() {
    return {
      loadedPost: {
        id: "Outdoor Humidity",
        topic: "/frontdoor/outside/humidity",
        message: "Exterior humidity is 25%",
        thumbnailLink:
          "https://www.homage.sg/wp-content/uploads/2018/09/47724337_l-1080x675.jpg"
      }
    };
  }
};
</script>
<style scoped>
.update-form {
  width: 90%;
  margin: 20px auto;
}
</style>