<template>
  <div class="home">
    <h2>{{ appTitle }}</h2>
    <div>
      <h3>{{ counterData.title }}</h3>
      <button @click="decreaseCounter" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter" class="btn">+</button>
    </div>
    <p>This number is {{oddOrEven}}</p>
    <div>
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text">
    </div>
  </div>
</template>

<script setup>
import { reactive, 
  ref, 
  computed, 
  watch, 
  onBeforeMount, 
  onMounted, 
  onBeforeUnmount, 
  onUnmounted, 
  onActivated,
  onDeactivated} from 'vue'

const appTitle = "My Counter App";

//const count = ref(0)

const counterData = reactive({
  count: 0,
  title: 'Hello World!'
})

watch(()=>counterData.count, (newValue)=>{
  if(newValue == 20){
    alert('Count is 20')
  }
})

const oddOrEven = computed(() => counterData.count % 2 === 0 ? 'even' : 'odd')

const increaseCounter = ()=>{
  counterData.count++
}

const decreaseCounter = ()=>{
  counterData.count--
}

onBeforeMount(()=>{
  console.log("Before Mount")
})

onMounted(()=>{
  console.log("Mounted")
})

onBeforeUnmount(()=>{
  console.log("Before Unmount")
})
onUnmounted(()=>{
  console.log("Unmounted") 
})

onActivated(()=>{
  console.log("Activated")
})

onDeactivated(()=>{
  console.log("Deactivated")
})
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