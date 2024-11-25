<script setup>
import { Link } from '@inertiajs/vue3';
import { ref } from 'vue';
const newTitle = ref("");
const newContent = ref("");
</script>
<template>
  <a href="/">aタグ</a>
  <Link href="/">Linkタグ</Link>
  <Link :href="route('inertia.index')">Linkタグ</Link>
  <Link :href="route('inertia.show', { id: 1})">ルートパラメーター</Link>

  <div class="mb-8"></div>

  <input type="text" name="newTitle" v-model="newTitle"><br>
  <input type="text" name="newContent" v-model="newContent"><br>
  <Link as="button" :href="route('inertia.store')"
  :data="{
    title: newTitle,
    content: newContent,
  }"
  method="post"
  >保存テスト</Link>
</template>