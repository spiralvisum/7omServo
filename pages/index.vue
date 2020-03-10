<template>
  <div>
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-brand href="#">
        NavBar
      </b-navbar-brand>

      <b-navbar-toggle target="nav-collapse" />

      <b-collapse id="nav-collapse" is-nav>
        <b-navbar-nav>
          <b-nav-item href="#">
            Link
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
    </b-navbar>
    <p>Icons</p>
    <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'twitter' }" style="font-size: 44px;" />
    <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'facebook' }" style="font-size: 44px;" />
    <font-awesome-icon :icon="{ prefix: 'fab', iconName: 'instagram' }" style="font-size: 44px;" />
  </div>
</template>

<script>
import Vue from 'vue'
import { NavbarPlugin } from 'bootstrap-vue'

Vue.use(NavbarPlugin)

export default {
}
</script>

<style>
</style>
