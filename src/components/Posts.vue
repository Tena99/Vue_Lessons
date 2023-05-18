<template>
  <form class="posts_form" @submit.prevent>
    <input v-bind:value="title" @input="title_2 = $event.target.value" type="text" placeholder="Title">
    <input v-bind:value="body" @input="body_2 = $event.target.value" type="text" placeholder="Description">
    <button type="button" @click="createPost">Submit</button>
  </form>

<div class="posts" v-for="post in posts"  :key="post.id">
  <h2> <strong>Title:</strong> {{post.title}}</h2>
  <p> <strong> Description: </strong> {{post.body}}</p>
</div>

</template>

<script>
export default {
  name: 'Vue-Posts',
  data() {
    return {
      posts: [
          {
            id: 1,
            title: "Fusce efficitur",
            body: "Lorem ipsum dolor sit amet, consectetur adipiscing elit. Donec eget lacus eget nibh sodales consequat non eu turpis. Cras hendrerit lacus eget tellus varius venenatis."
          },
        {
          id: 2,
          title: "Vivamus volutpat",
          body: "Class aptent taciti sociosqu ad litora torquent per conubia nostra, per inceptos himenaeos. Sed quis malesuada metus. "
        },
        {
          id: 3,
          title: "Vestibulum eget dapibus sem.",
          body: "Donec libero tellus, venenatis quis viverra vestibulum, consequat eget velit. Duis eget faucibus justo. Vestibulum vel velit euismod, fermentum elit ut, dignissim ligula."
        },
      ],
      title: "",
      body: ""
    }
  },

  methods: {
    createPost() {
      const newPost = {
        id: Date.now(),
        title: this.title_2,
        body: this.body_2,
      }
      this.posts.push(newPost)
      this.title = ""
      this.body = ""
    }
  }
}
</script>

<style scoped>
.posts_form {
  display: flex;
  flex-direction: column;
}

.posts_form input {
  padding: 10px;
  border: 1px solid #00c5c5;
  margin-bottom: 15px;
}

.posts_form input:focus-visible {
  outline: 1px solid #a5a5a5;
}

.posts_form button {
  background: transparent;
  border: 1px solid #00c5c5;
  width: 100%;
  padding: 10px;
  max-width: 100px;
  align-self: end;
  margin-bottom: 15px;
}

.posts {
  border: 2px solid #00c5c5;
  padding: 10px;
  box-sizing: border-box;
  margin-bottom: 15px;
}

.posts h2 {
  margin: 0 0 10px 0;
  font-weight: 400;
}

.posts p {
  width: 50%;
  margin: auto;
}

</style>
