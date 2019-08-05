<template>
  <el-card shadow="hover" :body-style="{padding:0}" class="post">
    <header slot="header" class="post-header">
      <h3>post header</h3>
      <small>
        <i class="el-icon-time"></i>
        {{new Date().toLocaleString()}}
      </small>
    </header>
    <div class="post-body">
      <img
        src="https://tripmydream.cc/travelhub/travel/block_gallery/90/004/default_90004.jpg?v7"
        alt="post image"
        class="post-img"
      />
    </div>
    <footer class="post-footer">
      <el-button round @click="openPost">Открыть</el-button>
      <span>
        <i class="el-icon-message"></i>
        12
      </span>
    </footer>
  </el-card>
</template>
<script>
export default {
  methods: {
    openPost() {
      const id = "test";
      this.$router.push(`/post/${id}`);
    }
  }
};
</script>
<style lang="scss" scoped>
.post {
  margin-bottom: 1.5rem;
}
.post-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.post-img {
  width: 100%;
  height: auto;
}
.post-body {
  margin-bottom: 1rem;
}
.post-footer {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 1rem;
}
</style>
