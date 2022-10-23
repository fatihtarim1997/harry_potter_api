<script setup>
const props = defineProps(["data"]);
const emit = defineEmits(["setName"]);

const nameHandler = (name) => {
  emit("setName", name);
};
</script>
<template>
  <button class="button" :class="data" @click="nameHandler(props.data)">
    {{ props.data }}
  </button>
</template>

<style>
.button {

  border: 1px solid rgba(27, 31, 35, 0.15);
  border-radius: 6px;
  box-shadow: rgba(27, 31, 35, 0.04) 0 1px 0,
    rgba(255, 255, 255, 0.25) 0 1px 0 inset;
  box-sizing: border-box;
  color: #fff;
  cursor: pointer;
  display: inline-block;
  margin: 10px 10px;
  font-size: 24px;
  font-weight: 500;
  line-height: 20px;
  list-style: none;
  padding: 16px 36px;
}
.gryffindor{
    background-color: #600002;
}
.slytherin{
    background-color: #003522;
}
.ravenclaw{
    background-color: #056083;
}
.hufflepuff{
    background-color: #e6c10f;
}
</style>
