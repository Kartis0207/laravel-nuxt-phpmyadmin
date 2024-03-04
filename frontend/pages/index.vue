<template>
  <div>
    <button
      type="button"
      name="button"
      @click="getMsg"
    >
      RailsからAPIを取得する
    </button>
    <div
      v-for="(msg, i) in msgs"
      :key="i"
    >
      {{ msg }}
    </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data () {
    return {
      msgs: []
    }
  },
  methods: {
    getMsg () {
      const baseURL = 'http://localhost:8000'
      
      // this.$axios.$get('/hello/index')
      axios.get(`${baseURL}/hello/index`)
        .then(res => this.msgs.push(res.data))
    }
  }
}
</script>
