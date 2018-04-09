<template>
  <div class="page">
    <button @click="handleClick">{{ counter }}</button>
    <p>{{ banner.name }}</p>
  </div>
</template>

<script>
import { mapState } from 'vuex'

export default {
  async asyncData ({ store, error }) {
    // 对 axios 进行批量处理
    let [ res ] = await Promise.all([
      store.dispatch('banner')
    ]).catch((e) => {
      error({ statusCode: 404, message: 'Post not found' })
    })
    return {
      banner: res.banner
    }
  },
  computed: {
    ...mapState({
      counter: state => state.counter
    })
  },
  methods: {
    handleClick () {
      this.$store.commit('INCREMENT')
    }
  }
}
</script>
