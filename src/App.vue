<template>
  <div>
    <h1>Mon clone Instagram</h1>
    <div class="card-container" >
      <div v-for="post in postList" :key="post.id">
        <CardComponent :post="post" v-on:like="like"/>
      </div>
    </div>
  </div>
</template>

<script>
import CardComponent from './components/CardComponent.vue';

export default {
  name: 'App',
  components: {
    CardComponent
  },
  data() {
    return {
      postList: [
        {
          "id": "1",
          "title": "Ma super app vuejs !",
          "content": "C'était un super projet",
          "imgUrl": "https://picsum.photos/200/300",
          "like": 0
        },
        {
          "id": "2",
          "title": "Ma super app react !",
          "content": "C'était un autre super projet",
          "imgUrl": "https://picsum.photos/200/300",
          "like": 0
        },
        {
          "id": "3",
          "title": "Ma super app angular !",
          "content": "Encore un super projet",
          "imgUrl": "https://picsum.photos/200/300",
          "like": 0
        },
        {
          "id": "4",
          "title": "Mon super Wordpress !",
          "content": "Pas fou ça",
          "imgUrl": "https://picsum.photos/200/300",
          "like": 0
        }
      ]
    }
  },
  methods: {
    like(post) {
      post.like++;
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
}
.card-container{
  display: flex;
  /* flex-direction: row; */
  flex-wrap: wrap;
  justify-content: space-around;
  width: 100%;
}
h1{
  text-align: center;
}
</style>
