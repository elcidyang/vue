<template>
  <div>
    <router-view/>
    <ul class="footer">
      <li class="icons">
        <router-link :to="{name:'list'}">新闻列表</router-link>
      </li>
      <li class="icons">
        <router-link :to="{name:'user'}">个人中心</router-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "Home",
  components: {},
  props: {},
  data() {
    return {};
  },
  watch: {},
  computed: {},
  methods: {},
  created() {},
  mounted() {}
};
</script>
<style scoped lang="scss">
li {
  list-style: none;
}
.footer {
  position: fixed;
  width: 100%;
  height: 60px;
  line-height: 60px;
  left: 0;
  bottom: 0;
  display: flex;
  justify-content: space-around;
}
.icons {
  font-size: 16px;
  flex: 1;
  text-align: center;
  border-top: 1px solid #42064d;
}
a {
  color: #42b983;
  display: block;
  &.active {
    color: #fff;
    background: #42064d;
  }
}
</style>