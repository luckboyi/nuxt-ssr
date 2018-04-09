<template>
    <div>
        <h3>news index page</h3>
        <p>newsId:{{$route.params.newsId}}</p>
        <ul>
            <li>
                <a href="/">home</a>
            </li>
            <li>
                <nuxt-link :to="{path:'/news/*',name:'deatil',params:{newsId:3306,title:'郑毅的新闻中心'}}" href="/news/1">news-1</nuxt-link>
            </li>
            <li>
                <a href="/news/2">news-2</a>
            </li>
        </ul>
    </div>
</template>
<script>
export default {
  data(){
      return {
          title:this.$route.params.title
      }
  },
  head() {
      return {
          title:this.title,
          meta:[
              {hid:'description',name:'news',content:'this is news page'}
          ]
      }
  }
}
</script>
