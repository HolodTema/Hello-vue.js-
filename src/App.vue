<template>
  <div class="app">
    <form>
      <h4>Post creating</h4>
      <input class="input"
             type="text"
             placeholder="Title"
             v-bind:value="title"
             @input="inputTitle">
      <input class="input" type="text" placeholder="Description" v-bind:value="body">
      <button class="btn" @click="createPost">Create</button>
    </form>
    <div class="post" v-for="post in posts" v-bind:key="post.id">
      <div><strong>Title: </strong>{{post.title}}</div>
      <div><strong>Description: </strong>{{post.body}}</div>
    </div>
  </div>

</template>

<script>
export default {
  data() {
    return {
      posts: [
        {id: 1, title: 'JavaScript', body: 'description'},
        {id: 2, title: 'JavaScript 2', body: 'description 2'},
        {id: 3, title: 'JavaScript 3', body: 'description 3'},
        {id: 3, title: 'JavaScript 4', body: 'description 4'},
        {id: 3, title: 'JavaScript 5', body: 'description 5'},
      ],
      title: '',
      body: '',
    }
  },

  methods: {
    createPost() {

    },

    inputTitle(event) {
      this.title = event.target.value;
    }
  }
}
</script>
<!--scoped is like private - access for styles will be only for this components-->
<style>
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
.app {
  padding: 20px;
}
.post {
  padding: 15px;
  border: 2px solid teal;
  margin-top: 15px;
}
form {
  display: flex;
  flex-direction: column;
}
.input {
  width: 100%;
  border: 1px solid teal;
  padding: 10px 15px;
  margin-top: 15px;
}
.btn {
  margin-top: 15px;
  align-self: flex-end;
  padding: 10px 15px;
  background: none;
  color: teal;
  border: 1px solid teal;

}
</style>