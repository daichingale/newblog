<template>
<div>
  <ul class="lists">
  <li :class="`list ${item.name}`" v-for="item in toc" :key="item.id">
   <n-link v-scroll-to="`#${item.id}`" to>
      {{ item.text }}
    </n-link>
  </li>
</ul>
  <main class="main">
    <h1 class="title">{{ title }}</h1>
    <p class="publishedAt">{{ publishedAt }}</p>
    <img :src="image.url" width=100%>
    <div class="post" v-html="body"></div>
  </main>
</div>
  
</template>

<script>
import axios from 'axios'

export default {
  head () {
    return {
      title : 'Blog',
    }
  },
  async asyncData({ params }) {
    const { data } = await axios.get(
      `https://smashbrosinfo.microcms.io/api/v1/blog/${params.slug}`,
      {
        headers:{"X-MICROCMS-API-KEY":"aae5a77d-d4c1-475d-9662-a4bef05133d8"}
      }
    )
    return data
  },
}


</script>

<style>
  h1 {
    font-size: 30px;
    font-weight: bold;
    margin: 40 0 20;
    background-color: #eee;
    padding: 10 20;
    border-radius: 5px;
  }
</style>