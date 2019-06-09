<template>
  <div class="wrapper">
    <label for="title">标题</label>
    <input id="title" type="text" v-model="title">
    <label for="content">内容</label>
    <input id="content" type="text" v-model="content">
    <div class="btn" @click="add()">添加</div>
  </div>
</template>

<script>
import store from "@/store";
export default {
  name: "add",
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