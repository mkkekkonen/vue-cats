<template>
  <tr>
    <td class="bold">{{ data.title }}</td>
    <td>{{ data.value }}</td>
  </tr>
</template>

<script>
export default {
  name: 'DataRow',
  props: {
    data: Object
  }
}
</script>

<style scoped>
td {
  padding: 0.25rem;
  vertical-align: top;
}

.bold {
  font-weight: bold;
}
</style>
