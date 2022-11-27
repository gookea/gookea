<template>
  请输入要进行 Base64 编码的字符
  <el-input type="textarea" v-model="txtA" :rows="6" placeholder="请输入要进行 Base64 编码的字符" @input="encode" />
  请输入要进行 Base64 解码的字符
  <el-input type="textarea" v-model="txtB" :rows="6" placeholder="请输入要进行 Base64 解码的字符" @input="decode" />
</template>
<script lang="ts">
export default {
  data() {
    return {
      txtA: "",
      txtB: "",
    };
  },
  methods: {
    encode() {
      this.txtB = Buffer.from(this.txtA).toString("base64");
    },
    decode() {
      this.txtA = Buffer.from(this.txtB, "base64").toString();
    },
  },
};
</script>
