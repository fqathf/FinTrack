<template>
  <b-card
    v-bind:img-src="article.img"
    img-alt="Card image"
    img-top
  >
    <b-card-text>
      <h4>{{ article.title }}</h4>
      <p>{{ article.content }}</p>
    </b-card-text>
  </b-card>
</template>
<script>
export default {
  props: {
    article: {
      type: Object,
      default: 'Untitled',
    },
  },
}
</script>
