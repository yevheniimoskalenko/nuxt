<template>
  <div>
    <el-container>
      <el-header>
        <AppNavigation />
      </el-header>
      <el-main>
        <nuxt />
      </el-main>
      <el-footer></el-footer>
    </el-container>
  </div>
</template>
<script>
import AppNavigation from "@/components/main/Navigation";
export default {
  components: {
    AppNavigation
  }
};
</script>


