<template>
  <v-app>
    <Loading :visible="loading" />
    <SnackBar :configSnack="snackbar" />
    <transition name="slide" mode="out-in">
      <router-view />
    </transition>
  </v-app>
</template>

<script>
import SnackBar from './components/commons/SnackBar'
import Loading from './components/commons/Loading'
import { mapState } from 'vuex'
export default {
  name: 'App',
  components: {
    SnackBar,
    Loading
  },
  data() {
    return {}
  },
  computed: {
    ...mapState(['snackbar', 'loading'])
  }
}
</script>

<style lang="scss">
.slide-enter-active,
.slide-leave-active {
  transition: opacity 0.3s, transform 0.5s;
}

.slide-enter,
.slide-leave-to {
  opacity: 0;
  transform: translateX(-30%);
}
</style>
