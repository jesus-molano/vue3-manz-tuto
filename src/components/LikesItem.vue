<script setup>
import { computed } from '@vue/reactivity';
import { Icon } from '@iconify/vue';
import { reactive } from 'vue';

const countState = reactive({ count: 0 });

const addLike = () => countState.count += 1;
const subLike = () => countState.count > 0 ? countState.count -= 1 : null;
const counterText = computed(() => `Likes: ${countState.count}`)
</script>

<template>
  <div class="likes">
    <div class="amountOfLikes">{{ counterText }}</div>
    <div class="buttons">
      <button class="button" @click="subLike">
        <Icon icon="akar-icons:thumbs-down" />
      </button>
      <button class="button" @click="addLike">
        <Icon icon="akar-icons:thumbs-up" />
      </button>
    </div>
  </div>
</template>


<style lang="scss" scoped>
.likes {
  width: min(100%, 100px);
  display: flex;
  flex-direction: column;
  align-items: center;
  align-self: flex-end;

  button {
    text-align: center;
    background-color: #818181;
    color: #fff;
    border-radius: 6px;
    margin: 2px;
    border: 1px solid transparent;
    padding: 0.4rem 0.8rem;

    &:first-child {
      background-color: #595963;
    }

    &:last-child {
      background-color: #479c6d;
    }
  }
}
</style>