<template>
  <div class="student-card">
    <div class="card">
      <img :src="student.image" />

      <h3>Student Name: {{ student.name }}</h3>
      <p>Major: {{ student.major }}</p>

      <button @click="viewDetail">View Detail</button>
    </div>
  </div>
</template>

<script setup>

//props
const props = defineProps({
  student: Object,
});

//emits
const emit = defineEmits(['view-detail'])

function viewDetail() {
    emit('view-detail', props.student)
}

</script>

<style scoped>
.student-card {
  display: flex;
  margin: 20px;
}

.card {
  width: 280px;
  border: 2px solid gray;
  text-align: center;
  padding-bottom: 15px;
}
.card img {
  width: 100%;
  height: 220px;
}

button {
    margin-top: 10px;
    cursor: pointer;
    padding: 8px 16px;
}
</style>
