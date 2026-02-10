<script setup>
defineProps({
  user: {
    type: Object,
    required: true
  },
  links: {
    type: Array,
    default: () => []
  }
})
</script>

<template>
  <article class="card">
    <img class="card__avatar" :src="user.avatar" :alt="user.name">
    <header class="card__header">
      <h1 class="card__title">{{ user.name }}</h1>
      <p class="card__location">{{ user.location }}</p>
      <p class="card__bio">{{ user.bio }}</p>
    </header>
    <nav>
      <ul class="list-reset list">
        <li class="list__item" v-for="link in links" :key="link.name">
          <a class="list__link" :href="link.url">{{ link.name }}</a>
        </li>
      </ul>
    </nav>
  </article>
</template>


<style scoped>
.card {
  width: 100%;
  max-width: clamp(20.5rem, 17.1031rem + 14.4936vw, 24.06rem);
  flex-shrink: 0;
  padding: clamp(1.563rem, 0.6689rem + 3.8148vw, 2.5rem);
  border-radius: 0.75rem;
  background-color: var(--grey-800);
}

.card__header {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 1.625rem;
}

.card__avatar {
  display: block;
  margin: 0 auto 1.875rem; /* 30px */
  width: 5.5rem;  /* 88px */
  height: 5.5rem;  /* 88px*/
  border-radius: 50%;
  object-fit: cover;
}

.card__title {
  margin: 0;
  font-size: 1.5rem;
  font-weight: 700;
  margin-bottom: 0.5625rem;
  font-family: 'Inter Custom', sans-serif;
}

.card__location {
  margin: 0;
  color: var(--green);
  font-size: 0.9375rem;
  margin-bottom: 1.75rem;
}

.card__bio {
  margin: 0;
  font-size: 0.9375rem;
}

.list {
  display: flex;
  flex-direction: column;
  gap: 1.0625rem;
}

.list__item {
  text-align: center;
  border-radius: 0.5rem;
  background-color: var(--grey-700);
  transition: background-color .3s ease-in-out;
}

.list__item:hover {
  background-color: var(--green);
}

.list__link {
  display: block;
  padding: 0.875rem;
  font-weight: bold;
  color: var(--white);
  transition: color .3s ease-in-out;
}

.list__item:focus:not(:focus-visible) {
  outline: none;
}

.list__item:hover .list__link {
  color: var(--grey-900);
}


</style>