<template>
  <div id="app">
    <router-view/>
  </div>
</template>

<style lang="scss">
  @import '@/scss/style.scss';
  @import '@/scss/fonts.scss';
#app {
  width: 100%;
  height: auto;
  font-family: 'Montserrat', sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  background-color: rgb(18,18,18);
  background: radial-gradient(1100px at right, rgb(63, 40, 15), rgb(18, 18, 18));
  background: -webkit-radial-gradient(1100px at right, rgb(63, 40, 15), rgb(18, 18, 18));
  background: -moz-radial-gradient(1100px at right, rgb(63, 40, 15), rgb(18, 18, 18));
  background: linear-radial-gradient(1100px at right, rgb(63, 40, 15), rgb(18, 18, 18));
  color: #ffffff;
}

</style>
