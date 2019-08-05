<template>
  <el-card shadow="always" :style="{width: '500px'}">
    <el-form ref="form" :model="controls" :rules="rules" @submit.native.prevent="onSubmit">
      <h2 class="text-center">Войти в панель администратора</h2>
      <el-form-item label="Логин:" prop="login">
        <el-input v-model.trim="controls.login" />
      </el-form-item>
      <div class="mb">
        <el-form-item label="Пароль:" prop="password" type="password">
          <el-input v-model.trim="controls.password" />
        </el-form-item>
      </div>
      <el-form-item>
        <el-button type="primary" round native-type="submit" :loading="loading">Войти</el-button>
      </el-form-item>
    </el-form>
  </el-card>
</template>
<script>
export default {
  layout: "empty",
  data() {
    return {
      loading: false,
      controls: {
        login: "",
        password: ""
      },
      rules: {
        login: [
          {
            required: true,
            message: "Введите логин",
            trigger: "blur"
          }
        ],
        password: [
          {
            required: true,
            message: "Введите пароль",
            trigger: "blur"
          },
          {
            min: 6,
            message: "Пароль не должен быть не менее 6 символов",
            trigger: "blue"
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
          try {
            const formData = {
              login: this.controls.login,
              password: this.controls.password
            };
          } catch (e) {
            this.loading = false;
          }
        }
      });
    }
  }
};
</script>
<style lang="scss" scoped>
</style>
