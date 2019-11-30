<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/logo.png">
    <div class="outer-container">
      <div class="inner-container">
        <StatusListItem
          v-for="status in statusCodes"
          v-bind:status="status"
          v-bind:key="status.spec_title"
        />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import StatusListItem from '@/components/StatusListItem.vue'
import statusCodes from '../data/status-codes.json'

export default {
  name: 'home',
  components: {
    // HelloWorld
    StatusListItem
  },
  data: () => ({
    statusCodes
  })
}
</script>

<style scoped>
.outer-container {
  display: flex;
  justify-content: center;
  padding-top: 40px;
}

.inner-container {
  display: inline-block;
}
</style>
