<script setup>
defineProps({ session: Object })
defineEmits(['toggle-complete', 'delete-session'])
</script>

<template>
  <div :class="{ completed: session.completed }">
    <h3>{{ session.subject }} - {{ session.topic }}</h3>
    <p>Method: {{ session.method }} | Date: {{ session.studyDate }}</p>
    <button @click="$emit('toggle-complete', session.id)">
      {{ session.completed ? 'Completed' : 'Mark as Completed' }}
    </button>
    <button @click="$emit('delete-session', session.id)">Delete</button>
  </div>
</template>