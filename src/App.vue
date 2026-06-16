<script setup>
import { ref } from "vue";

const selectStudent = ref(null)
//emit
function showDetail(student) {
  // console.log(student);
  selectStudent.value = student
}

function closeDetail() {
  selectStudent.value = null
}

import StudentList from "./components/StudentList.vue";
import StudentDetail from "./components/StudentDetail.vue";

const students = ref([
  {
    id: 1,
    name: "Dara",
    age: 20,
    major: "Web Development",
    image: "https://i.pravatar.cc/150?img=1",
  },
  {
    id: 2,
    name: "Sokha",
    age: 21,
    major: "Networking",
    image: "https://i.pravatar.cc/150?img=2",
  },
  {
    id: 3,
    name: "Vanna",
    age: 19,
    major: "Graphic Design",
    image: "https://i.pravatar.cc/150?img=3",
  },
  {
    id: 4,
    name: "Nita",
    age: 22,
    major: "Software Engineering",
    image: "https://i.pravatar.cc/150?img=4",
  },
]);
</script>

<template>
  <div class="container">
    <h1>Student Directory</h1>

    <StudentList 
      :students="students"
      @view-detail="showDetail"
     />

    <StudentDetail
      v-if="selectStudent"
      :student="selectStudent"
      @close="closeDetail"
     />
  </div>
</template>

<style scoped>

</style>

