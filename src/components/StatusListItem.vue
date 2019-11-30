<template>
  <div class="flexbox">
    <b>{{ status.code }}</b>
    &nbsp;&mdash;&nbsp;
    <span>{{ status.phrase }}</span>
  </div>
</template>

<script>
export default {
  name: 'StatusListItem',
  props: {
    status: Object
  }
}
</script>

<style scoped>
.flexbox {
  display: flex;
  font-size: 135%;
  padding: 0.5rem;
}
</style>
