<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <h1>{{ name }}</h1>
    <div id="subAppContainer" style="height: 400px">123</div>
  </div>
</template>

<script>
// import { registerMicroApps, start } from "qiankun";
import { loadMicroApp } from "qiankun";
export default {
  name: "HelloWorld",

  data() {
    return {
      name: "主应用测试--下面是子应用",
    };
  },
  props: {
    msg: String,
  },
  mounted() {
    this.$nextTick(() => {
        loadMicroApp({
          name: "nexbboxweb",
          entry: "//localhost:9000",
          container: "#subAppContainer",
        });
        //   registerMicroApps([
        //   {
        //     name: "nexbboxweb",
        //     entry: "//localhost:9000/ybx/ ",
        //     container: "#subAppContainer", // 和app.vue配置的节点
        //     activeRule: "/",
        //     props: {},
        //   },
        // ]);
        // // 启动 qiankun
        // start({
        //   prefetch: "all", // 预加载
        // });
    });
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
