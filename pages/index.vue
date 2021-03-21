<template>
  <div>
    <p>dene</p>
    <div v-for="article of articles">
    <nuxt-link  :to="article.path">{{article.title}}
    </nuxt-link>
      <p>{{'Description:'+article.description}}</p>
    </div>

    <nuxt-link to="about">About</nuxt-link>
  </div>
</template>

<script>

export default {
  async asyncData({$content, params}) {
    const articles = await $content('blog', params.slug).only(['title', 'description', 'slug']).sortBy('createdAt', 'asc').fetch();
    console.log(articles);
    return {articles};
  },

  data: () => ({
    selectedItem: 1,
    newMeeting: '',
    items: [
      {id: 1, text: 'Real-Time', done: false},
      {id: 2, text: 'Audience', done: false},
      {id: 3, text: 'Conversions', done: false},
    ],
  }),
}

</script>
