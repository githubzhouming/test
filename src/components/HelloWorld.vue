<script setup lang="ts">
import { ref ,computed} from 'vue'
import {useStore} from '../store/index'

defineProps<{ msg: string }>()
const store=useStore()
const showCount = computed(()=>{
  return store.getters['getCount']
})
const count=ref(0)
const addBtn=()=>{
  store.commit('setCount',++count.value)
}
</script>

<template>
  <h1>{{ showCount }}</h1>

  <button type="button" @click="addBtn">新增</button>
  
</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
