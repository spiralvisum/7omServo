<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="#">
        7om Servo
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse" />

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">
            (the wind, baby)
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <div class="text-center">
      <b-img rounded="circle" v-bind="mainProps" src="/5a94e0abb2c96bc6a9a94299ef3600d0.jpg" fluid alt="Fluid image" />
    </div>
  </div>
</template>

<script>
import Vue from 'vue'
import { NavbarPlugin, ImagePlugin } from 'bootstrap-vue'

Vue.use(ImagePlugin)
Vue.use(NavbarPlugin)

export default {
}
</script>

<style>
</style>
