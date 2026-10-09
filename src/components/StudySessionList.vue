<script setup>
import StudySessionItem from './StudySessionItem.vue'

defineProps({
  sessions: Array
})

defineEmits(['toggle-complete', 'delete-session'])
</script>

<template>
  <div class="session-list">
    <h3>Planned Study Sessions</h3>
    <p v-if="sessions.length === 0" class="empty-text">No study sessions found. Add one above!</p>
    <StudySessionItem 
      v-for="session in sessions" 
      :key="session.id" 
      :session="session"
      @toggle-complete="$emit('toggle-complete', $event)"
      @delete-session="$emit('delete-session', $event)"
    />
  </div>
</template>

<style scoped>
.session-list {
  margin-top: 1rem;
}
.empty-text {
  color: #666;
  font-style: italic;
}
</style>