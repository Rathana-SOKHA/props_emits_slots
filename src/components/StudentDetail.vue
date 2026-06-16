<script setup>
const props = defineProps({
  student: Object
})

const emit = defineEmits(['close'])

</script>

<template>
  <div>

    <h2>Student Information</h2>

    <p>Name: {{ student.name }}</p>

    <p>Age: {{ student.age }}</p>

    <p>Major: {{ student.major }}</p>

    <button @click="emit('close')">
      Close
    </button>

  </div>
</template>