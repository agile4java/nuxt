<template>
  <div class="admin-new-post-page">
    <section class="new-post-form">
      <form>
        <AppControlInput v-model="editedPost.id">Id</AppControlInput>

        <AppControlInput v-model="editedPost.topic">Topic</AppControlInput>

        <AppControlInput v-model="editedPost.thumbnailLink">Thumbnail Link</AppControlInput>

        <AppControlInput control-type="textarea" v-model="editedPost.message">Message</AppControlInput>

        <AppButton type="submit">Save</AppButton>

        <AppButton
          type="button"
          style="margin-left: 10px"
          btn-style="cancel"
          @click="onCancel"
        >Cancel</AppButton>
      </form>
    </section>
  </div>
</template>
<script>
import AppControlInput from "@/components/UI/AppControlInput";
</script>