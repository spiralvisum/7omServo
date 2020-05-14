<template>
  <div>
    <b-navbar toggleable="xl" type="dark" variant="dark" fixed="top">
      <b-navbar-brand :to="'/'">
        <img class="abnlogo" src="~assets/audiobooks-now-logo.png" />
      </b-navbar-brand>
      <b-collapse id="nav-collapse" is-nav class="flex-shrink-1 flex-grow-0">
        <b-navbar-nav>
          <b-nav-item :to="'/browse'">
            Browse
          </b-nav-item>
          <b-nav-item :to="'/how'">
            How it Works
          </b-nav-item>
          <b-nav-item :to="'/why'">
            Why AudiobooksNow?
          </b-nav-item>
          <b-nav-item :to="'/why'">
            Specials
          </b-nav-item>
          <b-nav-item :to="'/why'">
            Apps
          </b-nav-item>
          <b-nav-item :to="'/why'">
            Gift Center
          </b-nav-item>
        </b-navbar-nav>
      </b-collapse>
      <div class="d-flex flex-grow-1">
        <b-form class="mr-2 my-1 mx-1 w-100 d-inline-block">
            <b-input-group>
                <b-form-input type="search" class="form-control border border-right-0" placeholder="Search..." />
                <span class="input-group-append">
                    <button class="btn btn-outline-light border border-left-0" type="button">
                        <b-icon icon="search"></b-icon>
                    </button>
                </span>
            </b-input-group>
        </b-form>
      </div>
      <b-navbar-toggle class="order-first mx-2" target="nav-collapse" />
    </b-navbar>
  </div>
</template>

<style scoped>
.abnlogo{
  width: 157px;
  height: 32px;
}
</style>

<script>
import Vue from 'vue'
import { NavbarPlugin, IconsPlugin, InputGroupPlugin, FormInputPlugin, FormPlugin } from 'bootstrap-vue'

Vue.use(NavbarPlugin)
Vue.use(IconsPlugin)
Vue.use(InputGroupPlugin)
Vue.use(FormInputPlugin)
Vue.use(FormPlugin)

export default {
  components: {
  }
}
</script>
