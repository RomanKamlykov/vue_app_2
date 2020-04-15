<template>
  <div class="form">
    <form @submit.prevent="submitMethod">
      <textarea class="form__textarea" name="" id="" cols="" rows=""></textarea>
      <div class="form__button">
        <input type="submit" value="Написать консультанту">
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'Form',
    methods: {
      submitMethod: function(e) {
        if (e.target[0].value) {
          this.$emit('form-submit', Date.now(), e.target[0].value)
          e.target[0].value = '';
        }
      }
    }
  }
</script>
<style lang="scss">
  @import url('https://fonts.googleapis.com/css?family=PT+Sans&display=swap');
  .form {
    .form__textarea {
      font-family: Arial;
      font-size: 14px;
      padding: 5px;
      background: #FFFFFF;
      border: 1px solid #000000;
      border-radius: 1px;
      width: 100%;
      height: 60px;
      resize: none;
    }
    .form__button {
      text-align: center;
      line-height: 100px;
      input[type="submit"] {
        width: 281px;
        height: 43px;
        border: none;
        background: #FDD639;
        border-radius: 23px;
        padding: 0;

        font-family: 'PT Sans', sans-serif;
        font-weight: bold;
        font-size: 16px;
        line-height: 21px;

        cursor: pointer;
        &:hover { background: #fcca03; }
        &:active { background: #e3b602; }
      }
    }
  }
</style>