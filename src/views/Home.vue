<template>
  <Header :changeTheme="changeTheme"/>
  <main class="main">
    <h1 class="main__title">Сайт рецептов</h1>
    <section class="recipes" id="recepts">
      <div class="container">
        <h2 class="recipes__title">Рецепты</h2>
        <div class="recipes__block">
          <div v-for="rec in recipes" :key="rec.title" class="recipes__card">
            <h3 class="recipes__card-title">{{rec.title}}</h3>
            <img :src="rec.url" alt="recept" class="recipes__card-img">
            <p class="recipes__desc">
              {{rec.desc}}
            </p>
            <ol class="recipes__list">
              <li v-for="step in rec.steps" :key="step" class="recipes__list-item">{{step}}</li>
            </ol>
          </div>

        </div>
      </div>
    </section>
    <section class="item-add" id="add-recept">
      <div class="container">
      <h2 class="item-add__title">Добавить рецепт</h2>
      <form @submit.prevent action="" class="item-add">
        <input placeholder="Название" v-model="receptName" type="text" class="item-add__input">
        <input placeholder="Описание" v-model="receptDesc" type="text" class="item-add__input">
        <input v-for="input in inputs" v-model="input.value" :key="input" placeholder="Ингридиент" type="text" class="item-add__input">
        <button :onclick="addInput" class="item-add__btn">Добавить ингридиент</button>
        <button :onclick="addRecept" class="item-add__btn">Добавить</button>
      </form>
      </div>
    </section>
  </main>
  <Footer/>
</template>

<script>
import Header from '../components/Header';
import Footer from '../components/Footer';

export default {
  data () {
    return {
      receptName: '',
      receptDesc: '',
      inputs: [],
      recipes: [
        {
          title: 'Спагетти с грибами в сливочном соусе',
          url: 'http://img1.russianfood.com/dycontent/images_upl/327/sm_326488.jpg',
          desc: 'описание',
          steps: [
            'Cпагетти - 200 г',
            'Грибы (шампиньоны) - 300 г',
            'Грибы (шампиньоны) - 300 г',
            'Грибы (шампиньоны) - 300 г',
          ],
        },
        {
          title: 'Спагетти с грибами в сливочном соусе',
          url: 'https://img1.russianfood.com/dycontent/images_upl/16/big_15930.jpg',
          desc: 'Очень вкусные, нежные булочки с творогом а-ля ватрушки.',
          steps: [
            'Cпагетти - 200 г',
            'Грибы (шампиньоны) - 300 г',
            'Грибы (шампиньоны) - 300 г',
            'Грибы (шампиньоны) - 300 г',
          ],
        },
        {
          title: 'Спагетти с грибами в сливочном соусе',
          url: 'http://img1.russianfood.com/dycontent/images_upl/327/sm_326488.jpg',
          desc: 'описание',
          steps: [
            'Cпагетти - 200 г',
            'Грибы (шампиньоны) - 300 г',
            'Грибы (шампиньоны) - 300 г',
            'Грибы (шампиньоны) - 300 г',
          ],
        }
      ],
    }
  },
  methods: {
    changeTheme () {
      document.querySelector("body").classList.toggle('dark-theme');
    },
    addRecept () {
      if (!(this.receptDesc && this.receptName && this.inputs.length > 0)){
        return false;
      }
      this.recipes.push({
        title: this.receptName,
        url: 'http://img1.russianfood.com/dycontent/images_upl/327/sm_326488.jpg',
        desc: this.receptDesc,
        steps: this.inputs.map((item) => item.value),
      });
      this.receptName = '';
      this.receptDesc = '';
      console.log(this.inputs);
      this.inputs = [];
    },
    addInput () {
      this.inputs.push({
        value: '',
      });
    }
  },
  components: {
    Header,
    Footer
  }
}
</script>

<style lang="scss">


$red: #ff6b6b;
$sky-blue: #4ecdc4;
  .main__title{
    text-align: center;
  }
  .dark-theme{
    background-color: #333;
    color: white;
  }
  .container{
    max-width: 1200px;
    margin: 0 auto; 
    padding: 0px 20px;
  }
  .recipes{
    padding-bottom: 20px;
    &__title{
      text-align: center;
      font-size: 25px;
    }
    &__block{
      display: grid;
      width: 100%;
      grid-template-columns: 1fr 1fr 1fr;
    }
    &__card{
      width: 300px;
      padding: 10px;
      background-color: $red;
      border-radius: 10px;
      margin-bottom: 20px;
    }
    &__card-img{
      width: 100%;
    }
    
  }
  .item-add{
    &__input{
      width: 100%;
      height: 50px;
      margin-bottom: 20px;
    }
    &__btn{
      width: 100%;
      height: 50px;
      margin-bottom: 50px;
      background-color: $sky-blue;
      border: 0px;
      cursor: pointer;
      border-radius: 10px;
    }
  }
  @media (max-width: 964px){
    .recipes__block{
      grid-template-columns: 1fr;
    }
    .recipes__card{
      width: 100%;
    }
  }
</style>
