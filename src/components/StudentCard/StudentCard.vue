<script setup>
const props = defineProps(["data"]);
console.log(props.data);
</script>
<template>
  <div class="card__container" :class="data.house.toLowerCase()">
    <img class="round" :src="props.data.image" alt="user" />
    <h3 class="student__name">{{ props.data.name }}</h3>

    <p class="student__species">Species:{{ props.data.species }}</p>
  </div>
</template>
<style>
.card__container {

  border-radius: 5px;
  box-shadow: 0px 10px 20px -10px rgba(0, 0, 0, 0.75);
  color: #ffffff;
  padding-top: 30px;
  position: relative;
  width: 250px;
  max-width: 100%;
  text-align: center;
  margin: 10px;
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
.card__container .round {
  height: 150px;
  width: 150px;
  border-radius: 50%;
  padding: 7px;
}
.student__name {
  margin: 10px 0;
}

.student__species{
  font-size: 16px;
  line-height: 21px;
}
</style>
