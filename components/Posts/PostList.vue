<template>
  <section class="post-list">
    <PostPreview
      id="Outside Temp"
      :is-admin="isAdmin"
      topic="/frontdoor/outside/temp"
      message="Temperature 56 F"
      thumbnail="https://www.homage.sg/wp-content/uploads/2018/09/47724337_l-1080x675.jpg"
    />
  </section>
</template>
<script>
import PostPreview from "@/components/Posts/PostPreview";

export default {
  components: {
    PostPreview
  },
  props: {
    isAdmin: {
      type: Boolean,
      default: false
    }
  }
};
</script>
<style scoped>
.post-list {
  display: flex;
  padding: 20px;
  box-sizing: border-box;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
}
</style>