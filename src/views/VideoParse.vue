<template>
  <div id="app">
    <div>
      <select v-model="parse_url">
        <option
          v-for="item in parse_urls"
          :key="item.value"
          :value="item.value"
          >{{ item.label }}</option
        >
      </select>
      <input type="text" placeholder="请输入视频地址" v-model="address" />
      <button @click="parse">解析</button>
    </div>
    <div>
      <iframe
        :src="iframe_src"
        frameborder="0"
        scrolling="no"
        width="100%"
        height="480px"
        allowfullscreen
      ></iframe>
    </div>
  </div>
</template>

<script>
export default {
  name: "VideoParse",
  data() {
    return {
      parse_url: "http://xii999.com/?url=",
      address: "",
      iframe_src: "https://xii999.com/",
      parse_urls: [
        { label: "默认", value: "http://xii999.com/?url=" },
        { label: "通用1", value: "https://vip.jaoyun.com/index.php?url=" },
        { label: "通用2", value: "http://vip.jlsprh.com/?url=" },
        { label: "通用3", value: "http://vip.26db.cn/d/?url=" },
        { label: "通用4", value: "http://vip.26db.cn/g/?url=" },
        { label: "通用5", value: "http://vip.26db.cn/f/?url=" },
        { label: "通用6", value: "https://okjx.cc/?url=" },
        { label: "通用7", value: "http://jx.idc126.net/jx/?url=" },
        { label: "通用8", value: "http://jx.drgxj.com/?url=" },
        { label: "腾讯&B站", value: "https://jiexi.380k.com/?url=" },
        { label: "B站", value: "https://jx.xhfhttc.cn/jx/?url=" }
      ]
    };
  },
  computed: {
    full_url: function() {
      return this.parse_url + this.address;
    }
  },
  methods: {
    parse() {
      this.iframe_src = this.full_url;
    }
  }
};
</script>

<style scoped>
div {
  margin-bottom: 10px;
}

input {
  height: 25px;
  width: 60%;
  margin-right: 10px;
}
button {
  height: 30px;
  width: 10%;
  margin-right: 10px;
}
select {
  height: 30px;
  width: 20%;
  margin-right: 10px;
}
</style>
