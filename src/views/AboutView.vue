<template>
  <div class="about">
    <h1>{{name}}</h1>
    <h1>{{age}}</h1>
  </div>
</template>

<script>
export default {
  data(){},
  setup(){
    let name = '大谷'
    const age = 30

    return {
      name: name,
      age: age,
    }
  }
}
</script>
