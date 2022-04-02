<template lang="">
  <div class="container">
    <LocalCases />
  </div>
</template>
<script>
import axios from 'axios'
import LocalCases from '@/components/LocalCases.vue'

export default {
  components: {
    LocalCases
  },
  data() {
    return {
      countries: null,
      selectedCountry: null
    }
  },
  async mounted() {
    axios.get(`/countries`).then(response => {
      this.countries = response.data
    })
    console.log(this.countries)
  }
}
</script>
<style lang="scss">
.container {
  margin: 0 auto;
  width: 1140px;
}
</style>