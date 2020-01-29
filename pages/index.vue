<template>
  <div>
    <div class="block block-one">
      <vue-typer
        :text="[
          'Welcome to itoaki’s Portfolio!',
          'いとあきのポートフォリオへようこそ！',
          '欢迎来到伊藤彰的作品集！',
          'Willkommen in Itoakis Portfolio!',
          'Chào mừng đến với danh mục đầu tư của Itoaki!',
          'Добро пожаловать в портфолио Itoaki!',
        ]"
        :pre-type-delay="300"
        :erase-delay="70"
        erase-style="backspace"
        caret-animaton="smooth"
        class="headline"
      />
    </div>
    <div class="block block-two">
      <p>Two</p>
    </div>
    <div class="block block-three">
      <p>Three</p>
    </div>
    <div class="block block-four">
      <p>Four</p>
    </div>
    <div class="block block-five">
      <p>Five</p>
    </div>
  </div>
</template>
<script>
import { VueTyper } from 'vue-typer'
export default {
  layout: 'top',
  components: {
    VueTyper
  }
}
</script>
<style>
.block {
  width: 100%;
  height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  position: -webkit-sticky;
  position: sticky;
  top: 0;
}
p {
  display: inline-block;
  font-size: 60px;
  font-family: 'Great Vibes', cursive;
  padding: 0;
  margin: 0;
}
.block-one {
  background: #212E32;
  color: #ffffff;
  z-index: 100;
}

.vue-typer .custom.char.typed {
  color: #ffffff;
}
.vue-typer .custom.caret {
  background-color: #ffffff;
}
.block-two {
  background: #85937A;
  z-index: 200;
}
.block-three {
  background: #212E32;
  color: #fff;
  z-index: 300;
}
.block-four {
  background: #85937A;
  z-index: 400;
}
.block-five {
  background: #212E32;
  color: #fff;
  z-index: 500;
}
/*
.block-five {
  background: #85937A;
  background-image: url("/images/amanogawa.jpg");
  color: #ffffff;
  z-index: 110;
}
*/
</style>
