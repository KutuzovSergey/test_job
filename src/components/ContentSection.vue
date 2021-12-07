<template>
  <article class="content container-fluid">
    <div class="content__block">
      <div class="content__info">
        <div class="content__title">
          <h5>изогнутость 1000R </h5>
        </div>
        <div class="content__text">
          <p>Радиус кривизны в 1000R - это наибольший радиус кривизны у игровых мониторов. Он дает преимущества: снижает нагрузку на глаза, уменьшает количество бликов, увеличивает размеры воспринимаемого изображения и создает больший эффект погружения. Окунитесь в виртуальные миры вокруг вас и получите удовольствие от любимой игры и прекрасного обзора.</p>
        </div>
      </div>
      <div class="content__image content__image-first">
        <img src="@/assets/asset-dcc2vj-large.png">
      </div>
      <div class="content__info content__info-second">
        <div class="content__title">
          <h5>165hz частота обновления</h5>
        </div>
        <div class="content__text">
          <p>Частота обновления 165 Гц, что более чем в два раза больше по сравнению со стандартом 60 Гц, превращает игры в истенное удовольствие. Реализуйте потенциал своего видеоадаптера. Забудьте про разрывы изображения и попрощайтесь с размытым изображением. Почувствуйте как ваши рефлексы преобразуются в непосредственные действия. Никогда не оглядывайтесь.</p>
        </div>
      </div>
      <div class="content__image content__image-second">
        <img src="@/assets/asset-laputi-large.png">
      </div>
    </div>
  </article>
</template>

<script>
export default {
  name: 'Slider',
  props: {
  }
}
</script>

<style scoped lang="scss">
  @import '~bootstrap/dist/css/bootstrap.min.css';
  @import '@/scss/_mixins.scss';
  @import '@/scss/style.scss';

  .content{
    max-width: 2100px;
    height: auto;
    padding-top: 226px;

    &__block{
      width: 1190px;
      margin: auto;
      height: auto;
    }

    &__info{
      width: 595px;
    }

    &__info-second{
      margin-left: 50%;
    }

    &__title{
      text-align: left;
      width: 100%;
      height: auto;
    }

    &__title>h5{
      @include textBlock(37px, 1.3, #fbfafa);
      letter-spacing: 12px;
      text-transform: uppercase;
      text-shadow: 0 0 6px rgb(117, 70, 28), 0 0 30px rgb(111, 67, 30), 0 0 12px rgb(87, 54, 26), 0 0 21px rgb(55, 36, 21);
    }

    &__text{
      width: 100%;
      height: auto;
      text-align: left;
    }

    &__text>p{
      @include textBlock(16px, 1.75, #ffffff);
    }

    &__image>img{
      width: 100%;
      height: auto;
    }

    &__image-first{
      margin-top: 132px;
      margin-bottom: 340px;
    }

    &__image-second{
      margin-top: 57px;
      padding-bottom: 150px;
    }
  }

  @media (max-width: 2100px){
    .content{
      max-width: 2100px;

      &__block{
        width: 1050px;
      }

      &__info{
        width: 525px;
      }

      &__image-first{
        margin-bottom: 300px; 
      }
    }
  }
  @media (max-width: 1800px){
    .content{
      max-width: 1800px;
      padding-top: 200px;

      &__block{
        width: 900px;
      }
      &__info{
        width: 570px;
      }
    }
  }
  @media (max-width: 1500px){
    .content{
      max-width: 1500px;

      &__block{
        width: 1100px;
      }
      &__info{
        width: 750px;
        margin: auto;
      }
    }
  }
  @media (max-width: 1200px){
    .content{
      max-width: 1200px;
      padding-top: 150px;

      &__block{
        width: 900px;
      }
      &__info{
        width: 600px;
      }

      &__image-first{
        margin-bottom: 250px; 
      }
    }
  }
  @media (max-width: 960px){
    .content{
      width: auto;

      &__block{
        width: auto;
      }
      &__info{
        width: 80%;
        margin: auto;
      }

      &__title>h5{
        font-size: 22px;
        letter-spacing: 5px;
      }

      &__text>p{
        font-size: 12px;
      }

      &__image-first{
        margin-top: 50px;
        margin-bottom: 80px;
      }

      &__image-second{
        padding-bottom: 50px;
      }
    }
  }
</style>
