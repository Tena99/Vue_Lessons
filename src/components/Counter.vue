<template>
  <div class="counter">
    <div>Кол-во лайков: {{likes}} </div>
    <div>Кол-во дизлайков: {{dislikes}} </div>

    <button v-on:click="addLike">Like</button>
    <button v-on:click="addDislike">Dislike</button>

  </div>
</template>

<script>
export default {
  name: 'Vue-Counter',
  data() {
    return {
      likes: 0,
      dislikes: 0
    }
  },

  methods: {
    addLike() {
      this.likes += 1;
    },
    addDislike() {
      this.dislikes += 1;
    }
  }
}
</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
