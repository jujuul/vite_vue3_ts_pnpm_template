<template>
  <div>用户名:{{ mainStore.name }}<br />长度:{{ mainStore.nameLength }}</div>
  <hr />
  <n-button @click="updateName">修改store中的name</n-button>
</template>

<script setup lang="ts">
import { NButton } from "naive-ui";
import { useMainStore } from "@/store/main";

const mainStore = useMainStore();

const updateName = () => {
  // $patch 修改 store 中的数据
  mainStore.$patch({
    name: "名称被修改了,nameLength也随之改变了",
  });
};
console.log(import.meta.env);
console.log(import.meta.env.VITE_APP_WEB_URL);
</script>
