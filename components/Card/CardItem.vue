<template>
  <b-card
    :img-src="article.img"
    img-alt="Card image"
    img-top
  >
    <b-card-text>
      <h4>{{ article.title }}</h4>
      <p>{{ article.content }}</p>
      <b-button :to="'articles/' + article.id">Visit</b-button>
    </b-card-text>
  </b-card>
</template>
<script>
export default {
  props: {
    article: {
      type: Object,
      default() {
        return {}
      }
    },
  },
  computed: {
    localTask: {
      get () {
        return this.article
      },
      set (newValue) {
        this.$emit('update:article', newValue)
      }
    }
  }
}
</script>