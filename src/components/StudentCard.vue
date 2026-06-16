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
  /* justify-content: center; */
  margin: 20px;
}

.card {
  width: 280px;
  /* background: white;
  border-radius: 12px;
  overflow: hidden;
  box-shadow: 0 4px 10px rgba(0, 0, 0, 0.15);
  transition: transform 0.3s ease, box-shadow 0.3s ease;
  text-align: center;
  padding-bottom: 15px; */
  border: 2px solid gray;
  text-align: center;
  padding-bottom: 15px;
}

/* .card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 18px rgba(0, 0, 0, 0.2);
} */

.card img {
  width: 100%;
  height: 220px;
  object-fit: cover;
}

.card h3 {
  margin: 15px 10px 8px;
  font-size: 20px;
  color: #333;
}

.card p {
  margin: 0;
  color: #666;
  font-size: 16px;
}
button {
    margin-top: 10px;
    cursor: pointer;
    padding: 8px 16px;
}
</style>
