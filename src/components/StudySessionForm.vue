<script setup>
import { ref } from 'vue'
const emit = defineEmits(['add-session'])

const subject = ref('')
const topic = ref('')
const method = ref('Reading')
const studyDate = ref('')

const handleSubmit = () => {
  if (!subject.value || !topic.value || !studyDate.value) {
    alert('Please fill out all required fields!')
    return
  }
  emit('add-session', {
    subject: subject.value,
    topic: topic.value,
    method: method.value,
    studyDate: studyDate.value
  })
  // Reset form
  subject.value = ''
  topic.value = ''
  method.value = 'Reading'
  studyDate.value = ''
}
</script>

template>
  <form @submit.prevent="handleSubmit">
    <input v-model="subject" placeholder="Subject" required />
    <input v-model="topic" placeholder="Topic" required />
    <select v-model="method">
      <option value="Reading">Reading</option>
      <option value="Practice">Practice</option>
      <option value="Review">Review</option>
      <option value="Group Study">Group Study</option>
    </select>
    <input type="date" v-model="studyDate" required />
    <button type="submit">Add Study Session</button>
  </form>
</template>