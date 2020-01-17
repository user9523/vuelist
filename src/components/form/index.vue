<template>
  <div>
    <h3>Elment表单</h3>
    <hr />
    <k-form :model="model" :rules="rules" ref="loginForm">
      <k-form-item label="用户名" prop="username">
        <k-input v-model="model.username" autocomplete="off"></k-input>
      </k-form-item>
      <k-form-item label="密码" prop="password">
        <k-input
          type="password"
          v-model="model.password"
          autocomplete="off"
        ></k-input>
      </k-form-item>
      <k-form-item label="密码" prop="password">
        <botton @click="submitForm('loginForm')">搜索</botton>
      </k-form-item>
    </k-form>
  </div>
</template>
<script>
import KForm from "./Form";
import KInput from "./Input";
import KFormItem from "./Formitem";
export default {
  components: {
    KInput,
    KFormItem,
    KForm
  },
  data() {
    return {
      model: { usernameL: "tom", password: "" },
      rules: {
        username: [{ required: true, message: "请输入要用户名" }],
        password: [{ required: true, message: "请输入密码" }]
      }
    };
  },
  methods: {
    submitFrom(form) {
      this.$refs[form].validate(valid => {
        if (valid) {
          alert("请求登录!");
        } else {
          alert("校验失败!");
        }
      });
    }
  }
};
</script>
<style lang="scss" scoped></style>
