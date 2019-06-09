<template>
  <div class="wrapper">
    <button @click="login()">登录</button>
    <button @click="reg()">注册</button>
  </div>
</template>

<script>
export default {
  components: {},
  props: {},
  data() {
    return {};
  },
  watch: {},
  computed: {},
  methods: {
    login() {
      this.$router.push("/home/list");
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