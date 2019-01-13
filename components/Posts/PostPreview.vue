<template>
  <nuxt-link v-bind:to="postLink">
    <article class="post-preview">
      <div class="post-thumbnail" :style="{backgroundImage: 'url(' + thumbnail + ')'}"></div>
      <div class="post-content">
        <h1>{{ id }}</h1>

        <p>{{ message }}</p>
      </div>
      <div class="post-footer">
        <p>{{ topic }}</p>
      </div>
    </article>
  </nuxt-link>
</template>
<script>
export default {
  name: "PostPreview",
  props: {
    id: {
      type: String,
      required: true
    },
    isAdmin: {
      type: Boolean,
      required: true
    },
    topic: {
      type: String,
      required: true
    },
    message: {
      type: String,
      required: true
    },
    thumbnail: {
      type: String //path to thumbnail
    }
  },
  computed: {
    postLink() {
      return this.isAdmin ? "/admin/" + this.id : "/posts/" + this.id;
    }
  }
};
</script>
<style scoped>
.post-preview {
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #ccc;
  background-color: white;
  width: 90%;
}

a {
  text-decoration: none;
  color: black;
}

@media (min-width: 850px) {
  .post-preview {
    width: 420px;
    margin: 5px;
  }
}

.post-thumbnail {
  width: 100%;
  height: 200px;
  background-position: center;
  background-size: cover;
}

.post-content {
  padding: 10px;
  text-align: center;
}

.post-footer {
  background: #000000;
  color: #dddddd;
  text-align: center;
  font-size: 10px;
  padding-top: 5px;
  padding-bottom: 5px;
}

a:hover .post-content,
a:active .post-content {
  background-color: #ccc;
}
</style>