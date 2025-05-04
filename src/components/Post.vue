<template>
  <div class="bg-gray-800 p-4 rounded-xl shadow-md mb-4">
    <div class="flex items-center space-x-3">
      <img :src="post.avatar" class="w-10 h-10 rounded-full" />
      <div>
        <div class="font-semibold">@{{ post.user }}</div>
        <div class="text-sm text-gray-400">{{ post.time }}</div>
      </div>
    </div>
    <div class="mt-2">{{ post.content }}</div>
    <img v-if="post.mediaType === 'image'" :src="post.media" class="rounded-md my-3" />
    <video v-else-if="post.mediaType === 'video'" controls class="rounded-md w-full my-3">
      <source :src="post.media" type="video/mp4" />
    </video>
    <div class="flex justify-around mt-2 text-sm text-gray-400">
      <span>❤️ {{ post.likes }}</span>
      <span>💬 {{ post.comments }}</span>
      <span>🔄 {{ post.reposts }}</span>
    </div>
  </div>
</template>

<script lang="ts">
export default {
  props: {
    post: Object
  }
};
</script>