<template>
  <div>{{ obj.num }}</div>
  <button @click="btn">btn</button>
</template>

<script setup lang="ts">
import { ref, reactive } from "vue";
let num = ref(1);
let obj = reactive({
  num: 10,
});
function btn() {
  obj.num++;
}
</script>
<style lang="scss" scoped></style>
