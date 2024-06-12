<template>
  <div class="home">
    <h2>{{ appTitle }}</h2>
    <h3>{{ counterData.title }}</h3>
    <button @click="decreaseCounter" class="btn">-</button>
    <span class="counter">{{ count }}</span>
    <button @click="increaseCounter" class="btn">+</button>
    <div>
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text">
    </div>
  </div>
</template>

<script setup>
import { reactive, ref } from 'vue'

const appTitle = "My Counter App";

const count = ref(0)

const counterData = reactive({
  count: 0,
  title: 'Hello World!'
})

const increaseCounter = ()=>{
  count.value++
}

const decreaseCounter = ()=>{
  count.value--
}
</script>

<!--
<script>
import { ref } from 'vue'
export default {
  setup(){
    const count = ref(0)

    const increaseCounter = ()=>{
      count.value++
    }

    const decreaseCounter = ()=>{
      count.value--
    } 
  
    return {
      count,
      increaseCounter,
      decreaseCounter
    }
  }
}
</script>
-->

<!--
<script>
export default {
  data() {
    return {
      count: 0
    }
  },
  methods: {
    increaseCounter() {
      this.count++
    },

    decreaseCounter() {
      this.count--
    }
  }
}
</script>

-->
<style>
.home {
  text-align: center;
}
.btn, .counter {
  margin: 10px;
  font-size: 40px;
}
</style>