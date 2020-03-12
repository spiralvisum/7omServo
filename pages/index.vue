<template>
  <div>
    <Servonav />
    <div class="text-center">
      <b-img rounded="circle" v-bind="mainProps" src="/5a94e0abb2c96bc6a9a94299ef3600d0.jpg" fluid alt="Fluid image" />
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import { ImagePlugin } from 'bootstrap-vue'
import Servonav from '@/components/Servonav'

Vue.use(ImagePlugin)

export default {
  components: {
    Servonav
  }
}
</script>

<style>
</style>
