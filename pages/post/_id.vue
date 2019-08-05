<template>
  <article class="post">
    <header class="post-header">
      <div class="post-title">
        <h1>post title</h1>
        <nuxt-link to="/">
          <i class="el-icon-back"></i>
        </nuxt-link>
      </div>
      <div class="post-info">
        <small>
          <i class="el-icon-time"></i>
          {{new Date().toLocaleString()}}
        </small>
        <small>
          <i class="el-icon-view">23</i>
        </small>
      </div>
      <div class="post-image">
        <img
          src="https://tripmydream.cc/travelhub/travel/block_gallery/90/004/default_90004.jpg?v7"
          alt="post image"
          class="post-img"
        />
      </div>
    </header>
    <main class="post-content">
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis, ratione sed vitae error illo minima ipsa similique quis exercitationem qui.</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis, ratione sed vitae error illo minima ipsa similique quis exercitationem qui.</p>
      <p>Lorem ipsum dolor sit amet consectetur adipisicing elit. Debitis, ratione sed vitae error illo minima ipsa similique quis exercitationem qui.</p>
    </main>
    <footer>
      <!-- form -->
      <app-comment-form />
      <div class="comments" v-if="false">
        <app-comment v-for="comment in 5" :key="comment" :comment="comment" />
      </div>
      <div class="text-center" v-else>Комментариев нет!</div>
    </footer>
  </article>
</template>
<script>
import AppComment from "@/components/main/comment";
import AppCommentForm from "@/components/main/commentform";
export default {
  validate({ params }) {
    return Boolean(params.id);
  },
  components: {
    AppComment,
    AppCommentForm
  }
};
</script>
<style lang="scss" scoped>
.post {
  max-width: 600px;
  margin: 0 auto;
}
.post-title {
  display: flex;
  justify-content: space-between;
  margin-bottom: 1rem;
  align-items: center;
}
.post-info {
  display: flex;
  justify-content: space-between;
  margin-bottom: 0.5rem;
  align-items: center;
}
.post-image img {
  width: 100%;
  height: auto;
}
.post-header {
  margin-bottom: 1.5rem;
}
.post-content {
  margin-bottom: 2rem;
}
</style>
