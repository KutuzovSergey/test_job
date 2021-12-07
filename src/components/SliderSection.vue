<template>
  <div class="slider container-fluid">

    <div class="row slider__block slider__active">
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-p3vbgk-big.png" alt="screen">
      </div>
      <div class="col-6 slider__image">
          <img src="@/assets/asset-qgowo9-big.png" alt="screen">
      </div>
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-p1vbgk-big.png" alt="screen">
      </div>
    </div>

    <div class="row slider__block">
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-qgowo9-big.png" alt="screen">
      </div>
      <div class="col-6 slider__image">
        <img src="@/assets/asset-p1vbgk-big.png" alt="screen">
      </div>
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-pmlnhm-big.png" alt="screen">
      </div>
    </div>

    <div class="row slider__block">
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-p1vbgk-big.png" alt="screen">
      </div>
      <div class="col-6 slider__image">
        <img src="@/assets/asset-pmlnhm-big.png" alt="screen">
      </div>
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-ttyenk-big.png" alt="screen">
      </div>
    </div>

    <div class="row slider__block">
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-p1vbgk-big.png" alt="screen">
      </div>
      <div class="col-6 slider__image">
        <img src="@/assets/asset-ttyenk-big.png" alt="screen">
      </div>
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-p3vbgk-big.png" alt="screen">
      </div>
    </div>

    <div class="row slider__block">
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-ttyenk-big.png" alt="screen">
      </div>
      <div class="col-6 slider__image">
        <img src="@/assets/asset-p3vbgk-big.png" alt="screen">
      </div>
      <div class="col-3 slider__side-image">
        <img src="@/assets/asset-qgowo9-big.png" alt="screen">
      </div>
    </div>

    <div class="slider__arrow-block">
      <div class="slider__arrow slider__arrow-left" @click="switchForward">
        <div></div>
      </div>
      <div class="slider__arrow slider__arrow-right" @click="switchBack">
        <div></div>
      </div>
    </div>
    <div class="slider__see-gallery">
      <router-link to="/" class="slider__link">
        <span class="slider__link-text">See product gallery</span>
        <div class="slider__line"></div>
      </router-link>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Slider',
  components: {},
  props: {
  },
  data() {
    return {
      index: 0,
      numberSeconds: 4000,
    }
  },
  methods: {
    switchForward: function () {
      const slider_elements = document.querySelectorAll('.slider__block');

      const movementActive = (s) =>{

        for (let i = 0; i < slider_elements.length; i++) {
          slider_elements[i].classList.remove('slider__active');
        }
        slider_elements[s].classList.add('slider__active');
      }

      const next = () =>{
        if (this.index == slider_elements.length - 1) {
          this.index = 0;
          movementActive(this.index);
        } else {
          this.index++;
          movementActive(this.index);
        }
      }

      next();
    },
    switchBack: function () {
      const slider_elements = document.querySelectorAll('.slider__block');

      const movementActive = (s) =>{

        for (let i = 0; i < slider_elements.length; i++) {
          slider_elements[i].classList.remove('slider__active');
        }
        slider_elements[s].classList.add('slider__active');
      }

      const next = () =>{

        if (this.index == 0) {
          this.index = slider_elements.length - 1;
          movementActive(this.index);
        } else {
          this.index--;
          movementActive(this.index);
        }
      }

      next();
    }
  },
  mounted(){
    setInterval(this.switchForward, this.numberSeconds);
  }
}
</script>

<style scoped lang="scss">
  @import '~bootstrap/dist/css/bootstrap.min.css';
  @import '@/scss/_mixins.scss';
  @import '@/scss/style.scss';

  .slider{
    position: relative;

    &__block{
      display: none;
      height: auto;
    }

    &__image{
      display: flex;
    }

    &__image>img{
      width: 100%;
      height: auto;
      margin: auto;
    }

    &__side-image{
      display: flex;
    }

    &__side-image>img{
      width: 70%;
      height: auto;
      margin: auto;
    }

    &__see-gallery{
      width: 100%;
      height: auto;
    }

    &__link{
      width: 180px;
      margin: auto;
      display: block;
      @include textBlock(18px, 1.75, #ffffff);
      text-decoration: none;
    }

    &__line{
      width: 100%;
      height: 3px;
      background: #FDEE90;
      background: -webkit-linear-gradient(top left, #FDEE90, #DE502E);
      background: -moz-linear-gradient(top left, #FDEE90, #DE502E);
      background: linear-gradient(to bottom right, #FDEE90, #DE502E);
    }

    &__arrow-block{
      position: absolute;
      left: 26.1%;
      top: 47%;
      width: 48.4%;
      height: auto;
      display: flex;
      justify-content: space-between;
    }

    &__arrow {
      cursor: pointer;
      position: relative;
      width: 25px;
      height: 20px;
      margin: 10px;
    }
    &__arrow div {
        position: relative;
        top: 10px;
        width: 16px;
        height: 3px;
        background: #da1d56;
        background: -webkit-linear-gradient(top left, #da1d56, #ff9965);
        background: -moz-linear-gradient(top left, #da1d56, #ff9965);
        background: linear-gradient(to bottom right, #da1d56, #ff9965);
        left:0;
        display: block;
    }

    &__arrow div::after{
      content: '';
      position: absolute;
      width: 13px;
      height: 3px;
      top: -4px;
      background: #da1d56;
      background: -webkit-linear-gradient(top left, #da1d56, #ff9965);
      background: -moz-linear-gradient(top left, #da1d56, #ff9965);
      background: linear-gradient(to bottom right, #da1d56, #ff9965);
    }

    &__arrow-left div::after {
        right: 8px;
        transform: rotate(-45deg);
    }

    &__arrow-right div::after{
        right: -5px;
        transform: rotate(45deg);
    }

    &__arrow div::before{
      content: '';
      position: absolute;
      width: 13px;
      height: 3px;
      top: 4px;
      background: #da1d56;
      background: -webkit-linear-gradient(top left, #da1d56, #ff9965);
      background: -moz-linear-gradient(top left, #da1d56, #ff9965);
      background: linear-gradient(to bottom right, #da1d56, #ff9965);
    }

    &__arrow-left div::before {
        right: 8px;
        transform: rotate(45deg);
    }

    &__arrow-right div::before {
        right: -5px;
        transform: rotate(-45deg);
    }

    &__arrow:hover {
        animation: arrow-1 1s linear infinite;
    }

    @keyframes fadeIn {
      0% {opacity:0;}
      100% {opacity:1;}
    }

    @-moz-keyframes fadeIn {
      0% {opacity:0;}
      100% {opacity:1;}
    }
    @-webkit-keyframes fadeIn {
      0% {opacity:0;}
      100% {opacity:1;}
    }
    @-o-keyframes fadeIn {
      0% {opacity:0;}
      100% {opacity:1;}
    }

    @-ms-keyframes fadeIn {
      0% {opacity:0;}
      100% {opacity:1;}
    }

    &__active{
      display: flex!important;
      animation: fadeIn ease 3s;
      -webkit-animation: fadeIn ease 3s;
      -moz-animation: fadeIn ease 3s;
      -o-animation: fadeIn ease 3s;
      -ms-animation: fadeIn ease 3s;
    }
  }

  @media (max-width: 1800px){
    .slider{

      &__arrow-block{
        left: 25.3%;
        width: 50%;
      }
    }
  }
  @media (max-width: 1500px){
    .slider{
      &__arrow-block{
        top: 45%;
      }
      &__arrow {
        width: 22px;
        height: 15px;
        margin: 10px;
      }
      &__arrow div {
          top: 10px;
          width: 14px;
          height: 2px;
      }

      &__arrow div::after{
        width: 12px;
        height: 2px;
        top: -3px;
      }

      &__arrow-left div::after {
          right: 8px;
      }

      &__arrow-right div::after{
          right: -5px;
      }

      &__arrow div::before{
        width: 12px;
        height: 2px;
        top: 3px;
      }

      &__arrow-left div::before {
          right: 8px;
      }

      &__arrow-right div::before {
          right: -5px;
      }
    }
  }
  @media (max-width: 1200px){
    .slider{
    }
  }
  @media (max-width: 1050px){
    .slider{

      &__arrow-block{
        left: 0;
        width: 100%;
      }

      &__image{
        width: 90%;
        margin: auto;
      }
      &__side-image {
        display: none;
      }
    }
  }
  @media (max-width: 960px){
    .slider{
    }
  }
</style>
