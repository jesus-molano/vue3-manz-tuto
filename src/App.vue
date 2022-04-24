<script setup>
import CardItem from './components/CardItem.vue';
</script>

<template>
<div class="title-vue">
  <h1>My dog's family</h1>
  <svg class="logoImg"><image href="./assets/fingerprint.svg" fallback=""></image></svg>
</div>
  <div class="container">
    <CardItem cardTitle="Alay" parentage="Daughter" image="dog-1"> Alay is my dog, she is 5 years old and she is a bit grumpy but at the same time very loving. </CardItem>
    <CardItem cardTitle="Ray" parentage="Son" image="dog-2"> He is the smallest of the family. He is very afraid of Alay and wants nothing to do with her. </CardItem>
    <CardItem cardTitle="Thor" parentage="Father" image="dog-3"> Thor is the father of the family. He is very protective of his partner Ela. </CardItem>
    <CardItem cardTitle="Ela" parentage="Mother" image="dog-4"> Ela, at just one year old, had 5 children. She does not separate from Thor </CardItem>
  </div>
</template>

<style lang="scss">
@import '@/assets/base.css';

#app {
  font-family: Helvetica, sans-serif;
  color: #2c3e50;
}

.title-vue{
  text-align: center;
  margin: auto;
  width: min(100%, 400px);
}
.container{
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
}
.logoImg{
  width: min(100%, 100px);
  height:100px;
  image{
    width: inherit;
    height: inherit;
  }
}
</style>
