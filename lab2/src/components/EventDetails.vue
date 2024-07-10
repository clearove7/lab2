<script setup lang="ts">
  import { defineProps } from 'vue'
  import Event from '@/types/Event'
  
  const props = defineProps<{
    event: Event
  }>()
  </script>
  
  <style scoped>
  .event-details {
    display: flex;
    justify-content: flex-end;
    align-items: center;
    margin-top: 10px;
  }
  
  .category,
  .organizer {
    font-size: 16px; /* Adjust font size as needed */
    text-align: right;
    margin-right: 20px; /* Provide some margin between category and organizer */
  }
  </style>
  <template>
    <div class="event-details">
      <div class="category">{{ event.category }}</div>
      <div class="organizer">{{ event.organizer }}</div>
    </div>
  </template>
  