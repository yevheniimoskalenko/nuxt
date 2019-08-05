<template>
  <el-form ref="form" :model="controls" :rules="rules" @submit.native.prevent="onSubmit">
    <h1>Добавить комментарий</h1>
    <el-form-item label="Имя:" prop="name">
      <el-input v-model.trim="controls.name" />
    </el-form-item>
    <el-form-item label="Текст комментария:" prop="text">
      <el-input type="textarea" v-model.trim="controls.text" resize="none" :rows="2" />
    </el-form-item>

    <el-form-item>
      <el-button type="primary" round native-type="submit" :loading="loading">Добавить комментарий</el-button>
    </el-form-item>
  </el-form>
</template>
<script>
export default {
  data() {
    return {
      controls: {
        name: "",
        text: ""
      },
      rules: {
        name: [
          {
            required: true,
            message: "Имя не должно быть пустым",
            trigger: "blur"
          }
        ],
        text: [
          {
            required: true,
            message: "Поле для ввода не должно быть пустым",
            trigger: "blur"
          }
        ]
      }
    };
  },
  methods: {
    onSubmit() {
      this.$refs.form.validate(valid => {
        if (valid) {
          this.loading = true;
        }
      });
    }
  }
};
</script>
<style lang="scss" scoped>
</style>
