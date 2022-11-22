<template>
  <div>GrandChildren （孫）</div>
  <div>{{userLocation}}</div>
  <div>{{userGeolocation.longitude}}</div>
  <div>{{userGeolocation.latitude}}</div>
</template>

<script>
import { inject } from 'vue'

export default {
  setup() {
    const userLocation = inject('location', 'The Universe')
    const userGeolocation = inject('geolocation')

    return {
      userLocation,
      userGeolocation
    }
  }
}
</script>

<style>

</style>