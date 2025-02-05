<template>
  <div class="comments-container">
    <h1>Comments</h1>
    <ul>
      <li v-for="comment in comments" :key="comment.id" class="comment-item">
        <div class="comment-name">{{ comment.name }}</div>
        <div class="comment-text">{{ comment.comment }}</div>
      </li>
    </ul>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';
import { supabase } from '../lib/supabaseClient';

const comments = ref([]);

async function getComments() {
  const { data, error } = await supabase.from('comments').select();
  if (error) {
    console.error("Error fetching comments:", error);
  } else {
    comments.value = data;
  }
}

onMounted(() => {
  getComments();
});
</script>

<style scoped>
.comments-container {
  border: dashed black 1px;
  margin: 20px auto;
  padding: 20px;
  background-color: #806ea6;
  width: 100%;
  max-width: 600px;
  text-align: center;
}

.title {
  color: #f8f7f2;
}

.comment-item {
  display: flex;
  flex-direction: column;
  align-items: center;
  text-align: center;
  margin-bottom: 10px;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
}

.comment-name, .comment-text {
  color: #f8f7f2;
  word-wrap: break-word;
}
</style>