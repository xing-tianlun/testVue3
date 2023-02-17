<template>
  <div>{{ obj.num }}</div>
  <button @click="btn">btn</button>
  <div>{{ numArr }}</div>
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
let numArr = [2, 1, 34, 3, 2, 45, 22, 34, 4];
function bubbleSort(numArr: number[]) {
  for (let i = 0; i < numArr.length - 1; i++) {
    for (let j = 0; j < numArr.length - 1 - i; j++) {
      if (numArr[j] > numArr[j + 1]) {
        let temp = numArr[j];
        numArr[j] = numArr[j + 1];
        numArr[j + 1] = temp;
      }
    }
  }
  return numArr;
}
console.log(bubbleSort(numArr));

let numberArr2 = [2, 34, 3, 2, 45, 22, 34, 4, 10, 23, 1];
function selectSort(numArr: number[]) {
  for (let i = 0; i < numArr.length; i++) {
    let minIndex = i;
    for (let j = i + 1; j < numArr.length; j++) {
      if (numArr[j] < numArr[minIndex]) {
        minIndex = j;
      }
    }
    if (minIndex !== i) {
      let temp = numArr[minIndex];
      numArr[minIndex] = numArr[i];
      numArr[i] = temp;
    }
  }
  return numArr;
}
console.log(selectSort(numberArr2));
</script>
<style lang="scss" scoped></style>
