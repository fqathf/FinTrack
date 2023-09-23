<template>
  <div>
    <div class="container mt-3 w-75 d-flex justify-content-center flex-row py-5">
      <div
        class="container mt-2 w-50 d-flex justify-content-center align-items-start flex-column py-5"
      >
        <h1 class="text-left">
          Ayo catat <br />
          Keuanganmu di FinTrack!
        </h1>
        <button class="btn btn-primary mt-2">Catat Sekarang!</button>
      </div>
      <div class="container w-50 d-flex justify-content-end py-5">
        <img
          class="align-self-center"
          src="../assets/animation_llpzpsh2_small.gif"
          alt=""
          style="height: 400px; width: 400px; z-index: -10"
        />
      </div>
    </div>
    <div class="container py-5">
      <b-card-group deck style="overflow-x: scroll;">
        <CardItem
          v-for="(article, i) in resultQuery"
          :key="i"
          :article="article"
          :isGrid="isGrid"
        />
      </b-card-group>
    </div>
  </div>
</template>
<script>
import CardItem from '@/components/Card/CardItem.vue'

export default {
  components: {
    CardItem,
  },
  data() {
    return {
      articles: [
        {
          title: 'Judul Artikel 1',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?',
          img: 'https://images.unsplash.com/photo-1649282806617-c51bb282899c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=2070&q=80',
        },
        {
          title: 'Judul Artikel 2',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?',
          img: 'https://images.unsplash.com/photo-1635732646038-0a1a2fe3f2d6?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1074&q=80',
        },
        {
          title: 'Judul Artikel 3',
          content:
            'Lorem ipsum dolor sit amet, consectetur adipisicing elit. Placeat dolor explicabo sint quos exercitationem fugiat reiciendis assumenda. Ad quia veritatis, dolor odit, voluptas numquam modi porro eius reprehenderit ullam tenetur?',
          img: 'https://images.unsplash.com/photo-1640006807976-a6127e9d6fa0?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1171&q=80',
        },
      ],
    }
  },
  computed: {
    resultQuery() {
      return this.articles
    }
  },
}
</script>
<style></style>
