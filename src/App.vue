<template>
  <div>
    <transition name="fade">
      <router-view/>
      </transition>
      </div>
</template>

<script>
export default {
  name: 'App'
}
</script>


<style scoped>
.fade-enter-active, .fade-leave-active {
  transition: opacity .8s
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>