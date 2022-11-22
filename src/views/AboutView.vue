<template>
  <div class="about">
    <h1>{{name}}</h1>
    <h1>{{age}}</h1>
    <h1>ref:{{nameRef}}</h1>
    <h1>reactive:{{book.title}}</h1>
    <h1>reactive:{{book.author[0]}}</h1>
    <h1>reactivToRefs:{{titleRef}}</h1>
    <h1>reactivToRefs:{{authorRef[1]}}</h1>
  </div>
</template>

<script>
import { ref, reactive, toRefs } from 'vue'

export default {
  data(){},
  setup(){
    let name = '大谷'
    const age = 30

    const nameRef = ref('錦織')

    const book = reactive({
      title: 'タイトル',
      author: ['大谷', '伊藤']
    })

    const booktoRefs = reactive({
      titleRef: 'タイトル2',
      authorRef: ['大谷2', '伊藤2']
    })

    return {
      name,
      age,
      nameRef,
      book,
      ...toRefs(booktoRefs)
    }
  }
}
</script>
