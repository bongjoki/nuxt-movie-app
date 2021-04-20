<template>
  <v-row justify="center" align="center">
    <v-col cols="12" sm="8" md="6">
      <client-only>
        <div class="text-center">{{ data.movies }}</div>
      </client-only>
    </v-col>
  </v-row>
</template>

<script>
export default {
  components: {},
  async asyncData({ $axios }) {
    const { data } = await $axios.get('/list_movies.json', {
      params: {
        limit: 50,
      },
    })
    return data
  },
  data() {
    return {}
  },
}
</script>
<style lang="scss" scoped></style>
