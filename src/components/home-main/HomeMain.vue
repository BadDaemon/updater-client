<template>
  <div class="home-main">
    <navbar>
      <template v-slot:left>
      <span class="text">
        All devices
      </span>
      </template>
      <template v-slot:tabs>
        <router-link
            class="mobile-visible-tab tab"
            v-bind:to="{
              name: 'home_devices',
            }"
        >
          Devices
        </router-link>

        <router-link
            class="tab"
            v-bind:to="{
              name: 'home_changes',
            }"
        >
          Changes
        </router-link>

      </template>
    </navbar>

    <div class="content">
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import Navbar from '../navbar/Navbar.vue';

export default {
  name: 'HomeMain',
  components: {
    Navbar,
  },
}
</script>

<style scoped>
.home-main {
  display: flex;
  flex-direction: column;
}

.home-main .navbar {
  flex-shrink: 0;
}

.home-main .content {
  flex-grow: 1;
  overflow: auto;
}
</style>
