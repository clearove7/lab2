<script setup lang="ts">
import EventCard from '@/components/EventCard.vue'
import CategoryCard from '@/components/CategoryCard.vue'
import Event from '@/type/Event'
import { ref, onMounted } from 'vue'
import StudentCard from '@/components/StudentCard.vue'
import EventService from '@/services/EventService'
import StudentService from '@/services/StudentService'

const students = ref<Student[]>(null)

onMounted(() => {
  StudentService.getEvent()
    .then((response) => {
      // console.log(response.data)
      students.value = response.data
    })
    .catch((error) => {
      console.error('There was an error!', error)
    })
})
</script>

<template>
  <h1>Students List</h1>
  <!-- new element -->
  <div class="students">
    <StudentCard v-for="student in students" :key="student.id" :student="student" />
  </div>
</template>

<style scoped>
.students {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
