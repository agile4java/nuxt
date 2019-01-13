<template>
  <form @submit.prevent="onSave">
    <AppControlInput v-model="editedPost.id">Id</AppControlInput>

    <AppControlInput v-model="editedPost.topic">Topic</AppControlInput>

    <AppControlInput v-model="editedPost.thumbnailLink">Thumbnail Link</AppControlInput>

    <AppControlInput control-type="textarea" v-model="editedPost.message">Message</AppControlInput>

    <AppButton type="submit">Save</AppButton>

    <AppButton type="button" style="margin-left: 10px" btn-style="cancel" @click="onCancel">Cancel</AppButton>
  </form>
</template>
<script>
import AppControlInput from "@/components/UI/AppControlInput";
import AppButton from "@/components/UI/AppButton";

export default {
  components: {
    AppControlInput,
    AppButton
  },
  props: {
    post: {
      type: Object,
      required: false
    }
  },
  data() {
    return {
      editedPost: this.post
        ? { ...this.post }
        : {
            id: "",
            topic: "",
            thumbnailLink: "",
            message: ""
          }
    };
  },
  methods: {
    onSave() {
      // save Post
      console.log(this.editedPost);
    },
    onCancel() {
      // navigate back
      this.$router.push("/admin");
    }
  }
};
</script>