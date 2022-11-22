<template>
  <div class="about">
    <h1>{{name}}</h1>
    <h1>{{age}}</h1>
    <h1>{{nameRef}}</h1>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  data(){},
  setup(){
    let name = '大谷'
    const age = 30
    const nameRef = ref('錦織')
    console.log(nameRef)
    console.log(nameRef.value)

    return {
      name,
      age,
      nameRef
    }
  }
}
</script>
