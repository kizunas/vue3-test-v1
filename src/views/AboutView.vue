<template>
  <div class="about">
    <h1>{{name}}</h1>
    <h1>{{age}}</h1>
    <h1>ref:{{nameRef}}</h1>
    <h1>reactive:{{book.title}}</h1>
    <h1>reactive:{{book.author[0]}}</h1>
    <h1>reactivToRefs:{{titleRef}}</h1>
    <h1>reactivToRefs:{{authorRef[1]}}</h1>
    <button @click="btnClick">クリック</button>
    <button @click="btnClick2">クリック2</button>
    <h1>computed:{{totalPrice}}</h1>

  </div>
</template>

<script>
import { ref, reactive, toRefs, computed } from 'vue'

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

    const btnClick = () => {
      console.log(book.title)
    }

    const btnClick2 = e => {
      console.log(e)
    }

    const item = reactive({
      price: 100,
      number: 1
    })

    const totalPrice = computed(()=>{
      return item.price * item.number
    })

    return {
      name,
      age,
      nameRef,
      book,
      ...toRefs(booktoRefs),
      btnClick,
      btnClick2,
      item,
      totalPrice
    }
  }
}
</script>
