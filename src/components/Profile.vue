<template>
  <div class="profile">
    <div class="profile__image">
      <img src="../assets/vrostova_1.png" alt="">
      <!-- <img src="https://via.placeholder.com/300x600" alt=""> -->
    </div>
    <div class="profile__text">
        <div class="name">
          Вероника Ростова
        </div>
        <div class="position">
          Менеджер по продажам
        </div>
        <div class="statement">
          Подберу для вас самые лучшие предложения.<br>
          Мои услуги абсолютно бесплатны
        </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'Profile'
  }
</script>

<style lang="scss">
  .profile {
    display: flex;
    align-items: flex-start;

    .profile__image {
      background-color: white;
      border-radius: 50%;
      z-index: 2;

      img {
        width: 124px;
        height: 124px;
        vertical-align: top;
        border-radius: 50%;
        object-fit: cover;
      }
    }
    .profile__text {
      div {
        padding: 5px 10px;
        font-family: Arial;
      }
      .name {
        font-weight: bold;
        font-size: 16px;
        line-height: 20px;
        color: #333333;
      }
      .position {
        font-size: 12px;
        line-height: 20px;
        color: #808080;
      }
      .statement {
        margin: 0;
        padding: 5px 10px;
        position: relative;
        font-size: 14px;
        line-height: 20px;
        color: #333333;
        z-index: 1;

        &::before {
          content: '';
          height: 100%;
          width: calc(100% + 40px);
          background: #FFFBC8;
          border: 1px solid #DADADA;
          border-radius: 5px;
          position: absolute;
          top: 0;
          left: -40px;
          z-index: -1;
        }
      }
    }
  }
</style>