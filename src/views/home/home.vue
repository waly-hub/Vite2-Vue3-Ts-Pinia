<template>
  <div>
    <h1>HOME</h1>
    <HelloWorld :msg="msg"></HelloWorld>
  </div>
</template>

<script setup lang="ts">
import HelloWorld from "@/components/HelloWorld.vue"
import request from "@/service"
import { onMounted } from "vue"
const msg = "你好"
onMounted(async () => {
  const res = await request.get("/get", {})
  console.log("res", res)

  const post = await request.post("/post", { params: 123 })
  console.log("post", post)
})
</script>

<style lang="less" scoped></style>
