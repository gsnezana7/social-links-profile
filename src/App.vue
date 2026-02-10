
<script setup>
import UserCard from './components/UserCard.vue'
import Footer from './components/footer.vue'
import avatarImage from './assets/images/avatar-jessica.jpeg'
import { createApp } from 'vue';

const userData = {
  name: 'Jessica Randall',
  location: 'London, United Kingdom',
  bio: '"Front-end developer and avid reader."',
  avatar: avatarImage
}

const userLinks = [
  { name: 'GitHub', url: '#' },
  { name: 'Frontend Mentor', url: '#' },
  { name: 'LinkedIn', url: '#' },
  { name: 'Twitter', url: '#' },
  { name: 'Instagram', url: '#' },
]
</script>

<template>
  <main class="container">
    <UserCard :user="userData" :links="userLinks" />
  </main>
  <Footer />
</template>