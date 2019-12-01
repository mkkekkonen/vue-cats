<template>
  <div class="flexbox">
    <router-link v-bind:to="url">
      <b>{{ status.code }}</b>
      &nbsp;&mdash;&nbsp;
      <span>{{ status.phrase }}</span>
    </router-link>
  </div>
</template>

<script>
const interpolateLinkUrl = code => `/cat/${code}`

export default {
  name: 'StatusListItem',
  props: {
    status: Object
  },
  data: function() {
    return {
      url: interpolateLinkUrl(this.status.code)
    }
  }
}
</script>

<style scoped>
a:link, a:visited {
  color: #42b983;
  font-weight: bold;
  text-align: left;
  text-decoration: none;
}

.flexbox {
  display: flex;
  padding: 0.5rem;
}
</style>
