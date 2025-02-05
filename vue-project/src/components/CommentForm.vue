<template>
  <div class="comment-form-container">
    <h2>Leave a Comment!</h2>
    <form @submit.prevent="submitComment">
      <div class="form-group">
        <label for="name">Name:</label>
        <input type="text" id="name" v-model="name" required class="form-control" />
      </div>
      <div class="form-group">
        <label for="comment">Comment:</label>
        <textarea id="comment" v-model="comment" required class="form-control"></textarea>
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
      <div v-if="submissionStatus" class="mt-2">
        {{ submissionStatus }}
      </div>
    </form>
  </div>
</template>

<script setup>
import { ref } from 'vue';
import { supabase } from '../lib/supabaseClient';

const name = ref('');
const comment = ref('');
const submissionStatus = ref(null);
const tableName = 'comments'; // Name of your Supabase table

async function submitComment() {
  submissionStatus.value = "Submitting...";
  try {
    const { error } = await supabase.from(tableName).insert([{ name: name.value, comment: comment.value }]);
    if (error) {
      console.error("Error inserting comment:", error);
      submissionStatus.value = "Error submitting comment. Please try again.";
    } else {
      submissionStatus.value = "Comment submitted successfully!";
      name.value = ''; // Clear form fields
      comment.value = '';
    }
  } catch (err) {
    console.error("An unexpected error occurred:", err);
    submissionStatus.value = "An unexpected error occurred. Please try again later.";
  }
}
</script>

<style scoped>
.comment-form-container {
  border: dashed black 1px;
  margin: 20px auto;
  padding: 20px;
  background-color: #f8f7f2;
  width: 100%;
  max-width: 600px;
  text-align: center;
}

h2 {
  color: #806ea6;
}

.label {
  color: #806ea6;
}

.form-group {
  margin-bottom: 1rem;
  text-align: left;
}

.form-control {
  width: 100%;
  padding: 0.5rem;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  height: 40px;
}

textarea.form-control {
  height: 100px;
  resize: none;
}

.btn {
  padding: 0.5rem 1rem;
  background-color: #806ea6;
  color: white;
  border: none;
  border-radius: 4px;
  cursor: pointer;
}

.status-message {
  color: #806ea6;
}

.comment-form-container label {
  color: #806ea6;
}

</style>