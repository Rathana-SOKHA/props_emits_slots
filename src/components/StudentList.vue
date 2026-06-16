<template>
    <div class="student-list">
        <h1>Students List</h1>
        
        <!-- <div v-for="student in students" :key="student.id">
            {{ student.name }}
        </div> -->
        <StudentCard
            v-for="student in students" :key="student.id"
            :student="student"
            @view-detail="handleViewDetail"
         />
    </div>
</template>

<script setup>
import StudentCard from './StudentCard.vue';
// prop
    defineProps({
        students: Array
    })

// emit
const emit = defineEmits(['view-detail'])

function handleViewDetail (student) {
    // console.log(student);
    emit('view-detail', student)
}

</script>

<style scoped>
.student-list {
    border: 2px solid teal;
    display: flex;
}
</style>