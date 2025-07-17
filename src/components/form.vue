<template>
  <div>
    <form v-if="!submitted">
        <label for="title">Title:</label>
        <input type="text" v-model.lazy="title" id="title" name="title" required>
        <label for="text">Message:</label>
        <textarea id="text" v-model.lazy="text" name="text" required></textarea>
        <button v-on:click.prevent="post">Submit</button>
    </form>
    <h2 v-if="submitted">Your post has sumbmitted.</h2>
    <div id="preview">
        <p>Title:</p>
        <p>{{ title }}</p>
        <p>Message:</p>
        <p>{{ text }}</p>
    </div>
  </div>
</template>

<script>
export default {
  data () {
    return {
        submitted: false,
        title: '',
        text: ''
    }
  },
  methods: {
    post: function() {
        this.$http.post('https://jsonplaceholder.typicode.com/posts', {
            userId: 1,
            id: 1,
            title: this.title,
            body: this.text
        }).then(function(data) {
            this.submitted = true;
            console.log('Post successful!', data);
        }).catch(function(error) {
            console.error('There was an error!', error);
        });
    }
  }
}
</script>

<style scoped>
    form {
        text-align: center;
    }
    label {
        display: block;
        margin-top: 10px;
    }
    input {
        display: block;
        width: 100%;
        max-width: 300px;
        margin: 5px auto;
    }
    textarea {
        display: block; 
        width: 100%;
        max-width: 300px;
        height: 100px;
        margin: 5px auto;       
    }
    button {
        margin-top: 10px;
        margin-bottom: 10px;
        display: inline;  
    }
    #preview {
        padding: 10px 20px;
        border: 1px solid #ccc;
        border-radius: 5px;
        margin-top: 30px 0px;
        text-align: left;
    }
</style>