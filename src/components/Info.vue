<template>
  <div class="info">
    <div>
      <span class="header">Последние отзывы</span>
      <span class="link"><a href="#" @click.prevent="alert">Все отзывы</a></span>
    </div>

    <div>
      <span class="likes">
        <span class="icon" @click="alert"><img src="../assets/heart.svg" alt /></span>
        <span class="number">131</span>
      </span>
      <span class="comments">
        <span class="icon"><img src="../assets/chat.svg" alt /></span>
        <span class="number">14</span>
      </span>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Info',
    methods: {
      alert: function() {
        alert('work in progress');
      }
    }
  }
</script>
<style lang="scss">
  .info {
    display: flex;
    justify-content: space-between;
    span {
      font-family: Arial;
    }

    div:first-child {
      .header {
        font-weight: bold;
        font-size: 16px;
        color: #333333;
        ~ span { //adds padding-left for all following spans
          padding-left: 5px;
        }
      }
      .link {
        font-size: 14px;
        color: #005DA1;
      }
    }
    div:last-child {
      .likes {
        ~ span { //adds padding-left for all following spans
          padding-left: 5px;
        }
      }
      .icon {
        cursor: pointer;
        img {
          height: 14px;
          position: relative;
          top: 3px;
        }
      }
      .number {
        padding-left: 3px;
        font-size: 12px;
        line-height: 14px;
        color: #333333;
      }
    }
  }
</style>