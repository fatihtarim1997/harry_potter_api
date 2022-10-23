<script setup>
import axios from "axios";
import { onMounted, ref } from "vue";
import StudentCard from "./components/StudentCard/StudentCard.vue";
import Button from "./components/Button/Button.vue";

const houses = ["gryffindor", "slytherin", "ravenclaw", "hufflepuff"];
const students = ref([]);

const getStudents = async (name) => {
  const url = "https://hp-api.herokuapp.com/api/characters/house/";
  const response = await axios.get(url + name);
  return response.data;
};
const filterByHouse = async (name) => {
  students.value = await getStudents(name);
};

onMounted((name) => {});
</script>

<template>
  <div class="header">
    <Button
      v-for="house in houses"
      :data="house"
      @setName="filterByHouse"
    ></Button>
  </div>
  <div class="content">
    <StudentCard v-for="student in students" :data="student"></StudentCard>
  </div>
</template>

<style scoped>
.header {
  width: 100%;
  height: 200px;
  background: rgb(2, 0, 36);
  background: linear-gradient(
    180deg,
    rgba(2, 0, 36, 1) 0%,
    rgba(9, 9, 121, 1) 63%,
    rgba(18, 92, 107, 1) 100%
  );
  display: flex;
  justify-content: center;
  align-items: center;
  margin-bottom: 30px;
}
.content {
  display: flex;
  justify-content: center;
  flex-wrap: wrap;
  margin: 10px;
}
</style>
