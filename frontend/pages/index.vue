<template>
  <div>
    <button
      type="button"
      name="button"
      @click="getMsg"
    >
      LaravelからAPIを取得する
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
export default {
  data () {
    return {
      msgs: []
    }
  },
  methods: {
    getMsg () {
      
      this.$axios.$get('/hello/index')
        .then(res => this.msgs.push(res))
    }
  }
}
</script>
