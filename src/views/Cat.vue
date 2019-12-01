<template>
  <div class="container">
    <img v-bind:src="imageUrl" />

    <table>
      <tbody>
        <data-row
          v-for="data in dataValues"
          v-bind:data="data"
          v-bind:key="data.title"
        />
      </tbody>
    </table>

    <h3>Cats from <a href="https://http.cat/">http.cat</a> 🐱</h3>
  </div>
</template>

<script>
import DataRow from '@/components/DataRow.vue'
import statusCodes from '@/data/status-codes.json'

const getStatus = code => statusCodes.find(statusCode => statusCode.code === code)
const interpolateImageUrl = code => `https://http.cat/${code}.jpg`
const getDataValues = statusCode => [
  { title: 'Code', value: statusCode.code },
  { title: 'Phrase', value: statusCode.phrase },
  { title: 'Description', value: statusCode.description }
]

export default {
  name: 'Cat',
  components: {
    DataRow
  },
  props: {
    code: String
  },
  data: function() {
    return {
      statusCode: getStatus(this.code),
      imageUrl: interpolateImageUrl(this.code),
      dataValues: getDataValues(getStatus(this.code))
    }
  }
}
</script>

<style scoped>
img {
  margin-bottom: 5rem;
  max-width: 100%;
}

table {
  max-width: 500px;
  text-align: left;
}

.container {
  display: flex;
  flex-direction: column;
  align-items: center;
}
</style>
