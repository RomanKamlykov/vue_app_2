<template>
  <div class="comment">
    <div class="comment__header">
      <span class="author">{{name}}</span>
      <span class="date">{{formattedDate}}</span>
    </div>
    
    <div class="comment__body">
      <div class="text">
        {{text}}
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Comment',
    props: {
      name: String,
      date: Number,
      text: String
    },
    computed: {
      formattedDate: function() {
        return new Date(this.date).toLocaleString("ru", { year: 'numeric', month: 'long', day: 'numeric' });
      }
    },
  }
</script>
<style lang="scss">
  .comment {
    font-family: Arial;

    .comment__header {
      line-height: 40px;
      .author {
        font-weight: bold;
        font-size: 14px;
        color: #333333;
        ~ span { //adds padding-left for all following spans
          padding-left: 5px;
        }
      }
      .date {
        font-size: 12px;
        color: #808080;
      }
    }
    .comment__body {
      .text {
        padding: 20px;
        background: #F2FBFF;
        border: 1px solid #C4CBCF;
        box-shadow: 0px 4px 10px rgba(128, 128, 128, 0.1);
        font-size: 14px;
        line-height: 19px;
        position: relative;

        &::before {
          content: "";
          width: 20px;
          height: 20px;
          background-image: url(../assets/corner2.svg);
          background-repeat: no-repeat;
          position: absolute;
          top: -17px;
          left: 20px;
        }
      }
    }
  }
</style>