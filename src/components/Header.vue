<template>
  <header class="header">
    <div class="container">
      <div class="header__inner">
        <img src="" alt="" class="header__logo">
        <nav class="header__nav">
          <ul class="header__list">
            <li class="header__item"><a href="" class="header__list-link">Главная</a></li>
            <li class="header__item"><a href="" class="header__list-link">Главная</a></li>
            <li class="header__item"><a href="" class="header__list-link">Главная</a></li>
          </ul>
        </nav>
      </div>
    </div>
  </header>
</template>

<script>



</script>

<style lang="scss" scoped>
  $blue: #1a535c;
  $yellow: #ffe66d;
  .header{
    background-color: $yellow;
    &__inner{
      display: flex;
      justify-content: space-between;
      padding: 10px 0px;
    }
    &__list{
      display: flex;
      list-style: none;
    }
    &__list-link{
      text-decoration: none;
      color: $blue;
      font-family: 'Ubuntu', sans-serif;
      font-weight: 500;
      font-size: 20px
    }
    &__item + &__item{
      margin-left: 20px;

    }
  }
  .container{
    max-width: 1200px;
    margin: 0 auto;
  }
</style>
