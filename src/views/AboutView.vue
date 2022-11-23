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
    <div>watch:<input v-model="search"></div>
    <div>watchEffect:<input v-model="searchEffect"></div>
  </div>
</template>

<script>
import { ref, reactive, toRefs, computed, watch, watchEffect } from 'vue'

export default {
  data(){},
  setup(){
    let name = '大谷'
    const age = 30

  //ref
    const nameRef = ref('錦織')

  //reactive
    const book = reactive({
      title: 'タイトル',
      author: ['大谷', '伊藤']
    })

  //toRefs
    const booktoRefs = reactive({
      titleRef: 'タイトル2',
      authorRef: ['大谷2', '伊藤2']
    })

  //method
    const btnClick = () => {
      console.log(book.title)
    }

    const btnClick2 = e => {
      console.log(e)
    }

  //computed
    const item = reactive({
      price: 100,
      number: 1
    })

    const totalPrice = computed(()=>{
      return item.price * item.number
    })

  //watch
    const search = ref('')
    watch (search, (newValue, preValue) => {
      console.log(`watch: ${search.value}`)
      console.log(`newValue: ${newValue}`)
      console.log(`preValue: ${preValue}`)
    })

  //watchEffect
    const searchEffect = ref('')
    watchEffect(()=>{
      console.log(`watchEffect: ${searchEffect.value}`)
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
      totalPrice,
      search,
      searchEffect
    }
  }
}
</script>
