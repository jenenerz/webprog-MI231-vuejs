<template>
    <h1>Comments</h1>
    <ul>
      <li v-for="comment in comments" :key="comment.id">{{ comment.name }} {{ comment.comment }}</li>
    </ul>
  </template>
  
  <script></script>
  
  <style>
    #app > div {
      border: dashed black 1px;
      display: inline-block;
      margin: 10px;
      padding: 10px;
      background-color: #806ea6;
    }
  </style>

<script setup>
import { ref, onMounted } from 'vue'
import { supabase } from '../lib/supabaseClient'

const comments = ref([])

async function getComments() {
  const { data } = await supabase.from('comments').select()
  comments.value = data
}

onMounted(() => {
  getComments()
})

</script>


<style>
.comments-container {
  width: 80%;
  max-width: 900px;
  margin: 20px auto;
  padding: 15px;
  background-color: #f8f7f2;
  border-radius: 8px;
  box-shadow: 0 3px 8px rgba(0, 0, 0, 0.1);
}

.comments-container h1 {
  text-align: center;
  color: #603f8b;
}

.comments-list {
  list-style: none;
  padding: 0;
}

.comments-list li {
  padding: 10px;
  margin: 5px 0;
  background-color: #ddd;
  border-radius: 4px;
}

</style>