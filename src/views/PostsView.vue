<template>
  <div class="post">
    <h1>Posts</h1>

    <ul>
      <li>
        <RouterLink to="/postDetail/1">Post 1</RouterLink>
      </li>
      <li>
        <RouterLink to="/postDetail/2">Post 2</RouterLink>
      </li>
      <li>
        <RouterLink to="/postDetail/3">Post 3</RouterLink>
      </li>
    </ul>

    <textarea v-autofocus />
  </div>
</template>

<script setup>
import { vAutofocus } from '@/directives/vAutofocus';
</script>

<<style scoped>
  ul {
    margin-bottom: 30px;
  }
</style>