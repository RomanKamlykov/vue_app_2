<template>
  <div class="test">
    <div class="post">
      <Profile />
      <Results :results="results" />
      <Info />
      <Comment v-for="(comment, index) in comments" :key="index" :name="comment.name" :date="comment.date" :text="comment.text" />
    </div>

    <div class="form">
      <Form @form-submit="addComment" />
    </div>
  </div>
</template>

<script>
  import Profile from './Profile.vue'
  import Results from './Results.vue'
  import Info from './Info.vue'
  import Comment from './Comment.vue'
  import Form from './Form.vue'
  
  import comments from '../data/comments.json'
  import results from '../data/results.json'

  export default {
    name: 'Test',
    data: function () {
      return {
        comments: [],
        results: []
      }
    },
    components: {
      Profile,
      Results,
      Info,
      Comment,
      Form
    },
    created: function () {
      this.comments = comments;
      this.results = results;
    },
    methods: {
      addComment: function(time, text) {
        this.comments.push({
          id: "007",
          name: "James Bond",
          date: time,
          text: text,
        })
      }
    }
  }
</script>

<style lang="scss">
  .test {
    margin: auto;
    margin-top: 20px;
    background: #FFFFFF;
    min-width: 360px;
    max-width: 720px;

    >.post {
      padding: 20px;
      >.profile {
        .statement {
          @media screen and (max-width: 499px) {
            display: none;
          }
        }
      }
      >.results {
        padding-bottom: 20px;
        margin-left: 134px;
        @media screen and (max-width: 499px) {
          margin-left: 0px;
        }
      }
    }
    >.form {
      padding: 20px;
      background: #F2F2F2;
    }
  }
</style>