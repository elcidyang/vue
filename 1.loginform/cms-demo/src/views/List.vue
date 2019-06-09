<template>
  <div class="wrapper">
    <ul>
      <li v-for="(item,index) in pageList" :key="index">{{item.title}}-{{item.content}}</li>
    </ul>
  </div>
</template>

<script>
import store from "@/store";
export default {
  name: "List",
  store,
  components: {},
  props: {},
  data() {
    return {};
  },
  watch: {},
  computed: {
    pageList() {
      return store.state.lists;
    }
  },
  methods: {},
  created() {},
  mounted() {}
};
</script>
<style scoped>
.wrapper {
}
</style>