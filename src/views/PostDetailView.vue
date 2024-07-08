<template>
    <div class="post-detail">
      <h1>This is post page</h1>
      <div>
        <button @click="showPostId">Show</button>
      </div>
      <div>
        <button @click="goHomeIn3Seconds">Go home in 3 seconds</button>
      </div>
      <div>
        <button @click="goToFirstPost">Go home first post</button>
      </div>
      <p>Display the content of past ith ID of  {{ $route.params.id }}</p>
      <RouterLink to="/post"> &lt; Back</RouterLink>
    </div>
  </template>
  
  <script setup>
    import { useRoute, useRouter } from 'vue-router'
    const route = useRoute()
    const router = useRouter()
    const showPostId = () => {
      alert(`The id of the post is ${route.params.id}`)
    }

    const goHomeIn3Seconds = () => {
      setTimeout(() => {
        router.push({ name: 'home' })
      }, 3000)
    }

    const goToFirstPost = () => {
        console.log("goToFirstPost")
        router.push({ 
            name: 'postDetail', 
            params: { 
                id: 1 
            } 
        })
    }
  </script>