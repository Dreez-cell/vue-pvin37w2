<template>
  <div :class="darkMode ? 'bg-black text-white' : 'bg-white text-black'" class="min-h-screen font-sans">
    <Navigation :dark="darkMode" @toggleTheme="toggleDarkMode" />
    <main class="p-4">
      <Post v-for="post in posts" :key="post.id" :post="post" />
    </main>
  </div>
</template>

<script>
import Navigation from './components/Navigation.vue';
import Post from './components/Post.vue';

export default {
  name: 'App',
  components: { Navigation, Post },
  data() {
    return {
      darkMode: true,
      posts: [
        {
          id: 1,
          user: 'testagram_user',
          avatar: 'https://i.pravatar.cc/150?img=1',
          content: 'Just joined Testagram!',
          time: '2h ago',
          media: 'https://via.placeholder.com/600x400',
          mediaType: 'image',
          likes: 120,
          comments: 50,
          reposts: 15,
        },
        {
          id: 2,
          user: 'coder_kenya',
          avatar: 'https://i.pravatar.cc/150?img=2',
          content: 'Building something amazing with Vue!',
          time: '3h ago',
          media: 'https://www.w3schools.com/html/mov_bbb.mp4',
          mediaType: 'video',
          likes: 250,
          comments: 80,
          reposts: 30,
        }
      ],
    };
  },
  methods: {
    toggleDarkMode() {
      this.darkMode = !this.darkMode;
    }
  }
};
</script>

<style scoped>
body {
  font-family: 'Inter', sans-serif;
}
</style>