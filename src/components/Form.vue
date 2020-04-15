<template>
  <div class="form">
    <form @submit.prevent="submitMethod" @keyup.ctrl.enter="submitMethod">
      <textarea class="form__textarea" name="" id="" cols="" rows="" v-model="text">
      </textarea>
      <div class="form__button">
        <input type="submit" value="Написать консультанту">
      </div>
    </form>
  </div>
</template>

<script>
  export default {
    name: 'Form',
    data: function () {
      return {
        text: ''
      }
    },
    methods: {
      submitMethod: function() {
        if (this.text) {
          this.$emit('form-submit', Date.now(), this.text)
          this.text = '';
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