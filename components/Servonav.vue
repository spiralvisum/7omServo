<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand :to="'/'">
        7om Servo
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse" />

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item :to="'/vulx'">
            Vulx
          </b-nav-item>
          <b-nav-item :to="'/vulxform'">
            Vulx-Cacluator (Pots)
          </b-nav-item>
          <b-nav-item :to="'/vulxform2'">
            Vulx-Cacluator (Beds)
          </b-nav-item>
          <b-nav-item :to="'/navtest'">
            Navigation Dev
          </b-nav-item>          
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
  </div>
</template>

<script>
import Vue from 'vue'
import { NavbarPlugin } from 'bootstrap-vue'

Vue.use(NavbarPlugin)

export default {
  components: {
  }
}
</script>
