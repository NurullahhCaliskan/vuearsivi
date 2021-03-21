<template>
  <article>
    <nuxt-content :document="article"/>
    <p><span>Lorem ipsum dolor sit amet, consectetur adipisicing elit. Assumenda, consequatur.</span><span>Debitis delectus deserunt explicabo ipsa laudantium magni odit reprehenderit tenetur.</span><span>Doloribus eum minus nesciunt odit perferendis quae reiciendis temporibus vel.</span><span>Aspernatur autem delectus doloremque est ex, odio porro repudiandae! Dicta!</span><span>Aperiam asperiores at dolore dolorem eum hic, laboriosam nobis tempora.</span><span>Alias, blanditiis doloribus ducimus facere facilis iusto laboriosam perspiciatis quos.</span><span>Culpa, ea et facilis harum hic impedit mollitia officia similique.</span><span>Beatae, magni non perspiciatis quasi quis reprehenderit sequi veniam voluptas?</span><span>Aliquam dignissimos et ipsam laudantium maxime officia qui rerum voluptatum.</span><span>Iste nobis porro repellat repudiandae ut. Aut ducimus omnis temporibus.</span></p>
  </article>
</template>

<script>
export default {
  async asyncData({$content, params}) {
    const article = await $content('blog', params.slug).fetch();
    return {article}
  }
}
</script>
