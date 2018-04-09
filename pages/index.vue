<template>
  <div>
    <ul>
      <li>
        <nuxt-link :to="{name:'index'}">home</nuxt-link>
      </li>
      <li>
        <nuxt-link :to="{name:'about'}">about</nuxt-link>
      </li>
      <li>
        <nuxt-link :to="{name:'news',params:{newsId:3306,title:'郑毅的新闻中心'}}">news</nuxt-link>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  components: {
  }
}
</script>

<style>

</style>
