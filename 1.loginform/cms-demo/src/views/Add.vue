<template>
  <div class="wrapper">
    <label for="title">标题</label>
    <input id="title" type="text" v-model="title">
    <div>
      <label for="content">内容</label>
      <input id="content" type="text" v-model="content">
    </div>

    <button class="btn" @click="add()">添加</button>
  </div>
</template>

<script>
import store from "@/store";
export default {
  name: "Add",
  components: {},
  props: {},
  data() {
    return {
      title: "",
      content: ""
    };
  },
  watch: {},
  computed: {},
  methods: {
    add() {
      store.commit("addItem", { title: this.title, content: this.content });
      this.title = "";
      this.content = "";
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