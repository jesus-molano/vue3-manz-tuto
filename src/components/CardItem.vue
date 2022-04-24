<script setup>
import LikesItem from './LikesItem.vue';

defineProps({
  cardTitle: {
    type: String,
    default: "Dog",
    validator: value => value.length > 2
  },
  parentage: {
    type: String,
    default: "Father",
    validator: value => ["mother", "father", "son", "daughter"].includes(value.toLowerCase())
  },
  image: {
    type: String,
    required: false
  }
})
</script>

<template>
  <div class="card">
    <img :src="'/images/' + image + '.jpg'" alt="cardTitle">
    <div class="content">
      <h1>{{ cardTitle }}</h1>
      <h2>{{ parentage }}</h2>
      <p>
        <slot></slot>
      </p>
      <LikesItem />
    </div>
  </div>
</template>

<style  lang="scss" scoped>
.card {
  border: 1px solid #333;
  border-radius: 1rem;
  box-shadow:
    -4px -4px 20px #ccc,
    5px 5px 10px #aaa;
  width: min(100%, 400px);
  overflow: hidden;
  margin: 10px 20px;

  img {
    width: inherit;
    max-height: 200px;
    object-fit: cover;
    object-position: center;
  }

  .content {
    padding: 1.2rem 2.5rem;
    display: flex;
    flex-direction: column;

    h1,
    h2 {
      font-family: "Montserrat", sans-serif;
    }

    h1 {
      color: #333;
      margin: 0;
      font-weight: 700;
    }

    h2 {
      margin: 0;
      color: #999;
      font-weight: 400;
    }
  }
}
</style>