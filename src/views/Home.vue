<template>
  <div class="home">
    <img alt="Vue logo" src="../assets/kitty.png">
    <h1>HTTP Cats (with Vue)</h1>
    <div class="outer-container">
      <div class="inner-container">
        <h2>Status codes from <a href="https://github.com/for-GET/know-your-http-well">know-your-http-well</a></h2>
        <StatusListItem
          v-for="status in statusCodes"
          v-bind:status="status"
          v-bind:key="status.code"
        />
        <div class="icon-credit">Cat icon made by <a href="https://www.flaticon.com/authors/freepik" title="Freepik">Freepik</a> from <a href="https://www.flaticon.com/" title="Flaticon">www.flaticon.com</a></div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
// import HelloWorld from '@/components/HelloWorld.vue'
import StatusListItem from '@/components/StatusListItem.vue'
import statusCodes from '@/data/status-codes.json'

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
a:link, a:visited {
  color: #42b983;
  font-weight: bold;
  text-decoration: none;
}

.outer-container {
  display: flex;
  justify-content: center;
}

.inner-container {
  display: inline-block;
}

.icon-credit {
  padding: 1.5rem 0;
}
</style>
