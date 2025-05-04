<template>
  <div class="mb-4 p-4 bg-gray-800 rounded-lg shadow">
    <textarea 
      v-model="content"
      class="w-full bg-transparent border-none outline-none text-white placeholder-gray-400" 
      rows="3" 
      placeholder="What's happening? #hashtag @mention"
    ></textarea>
    <div class="text-right mt-2">
      <button 
        @click="createPost"
        class="bg-blue-500 px-4 py-1 rounded text-white hover:bg-blue-600 transition-colors"
      >
        Post
      </button>
    </div>
  </div>
</template>

<script>
export default {
  name: 'CreatePost',
  data() {
    return {
      content: ''
    }
  },
  methods: {
    createPost() {
      if (this.content.trim()) {
        this.$emit('create-post', {
          content: this.content,
          time: 'Just now',
          likes: 0,
          comments: 0,
          reposts: 0,
          user: 'current_user',
          avatar: 'https://i.pravatar.cc/150?img=3'
        });
        this.content = '';
      }
    }
  }
}
</script>