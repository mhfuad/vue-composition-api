<template>
  <div class="home">
    <h2 ref="appTitleRef">{{ appTitle }}</h2>
    <div>
      <h3>{{ counterData.title }}</h3>
      <button @click="decreaseCounter(2)" class="btn">--</button>
      <button @click="decreaseCounter(1)" class="btn">-</button>
      <span class="counter">{{ counterData.count }}</span>
      <button @click="increaseCounter(1)" class="btn">+</button>
      <button @click="increaseCounter(2)" class="btn">++</button>
    </div>
    <p>This number is {{oddOrEven}}</p>
    <div>
      <h4>Edit counter title:</h4>
      <input v-model="counterData.title" type="text" v-autofocus="true">
    </div>
  </div>
</template>

<script setup>
/*
  imports
*/
import { reactive, 
  ref, 
  computed, 
  watch, 
  onBeforeMount, 
  onMounted, 
  onBeforeUnmount, 
  onUnmounted, 
  onActivated,
  onDeactivated,
  onBeforeUpdate,
  onUpdated,
  nextTick
} from 'vue'

import { vAutofocus } from '@/directives/vAutofocus';

/*
  app title
*/
const appTitle = "My Counter App";
const appTitleRef = ref(null);

onMounted(()=>{
  console.log("Mounted")
  console.log(`The app title is: ${appTitleRef.value.offsetWidth} px width`)
})
/*
  counter
*/
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

const increaseCounter = async (amount)=>{
  counterData.count+= amount
  await nextTick()
  console.log("do something when counter has updated in the dom.")
}

const decreaseCounter = amount=>{
  counterData.count-= amount
}

onBeforeMount(()=>{
  console.log("Before Mount")
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

onBeforeUpdate(()=>{
  console.log("Before Update")
})

onUpdated(()=>{
  console.log("Updated")
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