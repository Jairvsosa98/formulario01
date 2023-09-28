<template>
  <NavBarView />
  <div class="container">
    <router-view />
  </div>
</template>

<script>
import NavBarView from '@/components/NavBarView.vue'
export default {
  components: {
    NavBarView
  }
}
</script>
