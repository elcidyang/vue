<template>
  <div class="wrapper">
    <form v-if="!isReg">
      <div>
        <label for="name">用户名</label>
        <input type="text" id="name" v-model="name">
      </div>
      <div>
        <label for="pwd">密码</label>
        <input type="text" id="pwd" v-model="password">
      </div>
      <div>
        <button @click.prevent="login()">登录</button>
        <button @click.prevent="reg()">注册</button>
      </div>
    </form>
    <form v-else>
      <div>
        <label for="name">用户名</label>
        <input type="text" id="name" v-model="name">
      </div>
      <div>
        <label for="pwd">密码</label>
        <input type="text" id="pwd" v-model="password">
      </div>
      <div>
        <label for="repwd">再次输入密码</label>
        <input type="text" id="repwd" v-model="repeat">
      </div>
      <div>
        <button @click.prevent="addUser()">确定</button>
        <button @click.prevent="cancel()">取消</button>
      </div>
    </form>
  </div>
</template>

<script>
export default {
  name: "Login",
  components: {},
  props: {},
  data() {
    return {
      isReg: false,
      name: "",
      password: "",
      repeat: ""
    };
  },
  watch: {},
  computed: {},
  methods: {
    login() {
      if (
        this.name === localStorage.getItem("name") &&
        this.password === localStorage.getItem("password")
      ) {
        this.$router.push("/home/list");
      } else {
        alert("不正确");
      }
    },
    reg() {
      this.isReg = true;
    },
    addUser() {
      if (this.repeat !== this.password) {
        alert("不一致");
        return;
      }
      localStorage.setItem("name", this.name);
      localStorage.setItem("password", this.password);
      this.name = "";
      this.password = "";
      this.repeat = "";
      this.isReg = false;
    },
    cancel() {
      this.isReg = false;
    }
  },
  created() {},
  mounted() {}
};
</script>
<style scoped>
.wrapper {
}
</style>