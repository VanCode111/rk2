<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__inner">
        <p class="footer__fio">
          Елисеев Иван Павлович
        </p>
        <p class="footer__group">201-322</p>
      </div>
    </div>
  </footer>
</template>

<script>



</script>

<style lang="scss" scoped>
  $blue: #1a535c;
  $yellow: #ffe66d;
  $white: #F7FFF7;
  .footer{
    color: $white;
    background-color: $blue;
    &__inner{
      padding: 10px 0px;
      display: flex;
      justify-content: space-between;
    }
  }
  .container{
    max-width: 1200px;
    margin: 0 auto;
  }
</style>
