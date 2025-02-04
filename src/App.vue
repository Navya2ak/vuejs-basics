
<script setup> // Composition API
import {ref} from "vue"

const name=ref("navya")
const tasks=ref(['kuli','kazhi','sleep'])
const task=ref('')

const toggle=()=>{
name.value=name.value+name.value
}

const addTask=()=>{
if(task.value.length!=0){
  tasks.value.push(task.value)
  task.value=''
}
}

const removeTask=(index)=>{
  tasks.value.splice(index,1)
}
</script>
<template>
  <form @submit.prevent="addTask">
  <label for="tasks"></label>
  <input type="text" name="task" id='task' v-model="task">
  <button type="submit">SUBMIT</button>
</form>
  <ol>
    <li v-for="(t,i) in tasks" key="t">{{ t }} <button @click="removeTask(i)">-</button></li>
  </ol>
  

</template>