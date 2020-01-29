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
      <div>
        <h2><span class="title_one">A</span>bout this site</h2>
        <p>
          このサイトは、<span class="inpact">圧倒的成長</span>と<span class="inpact">楽しく働くこと</span>を追求するいとあきのポートフォリオです。
          普段のアウトプットや、アカウントなどをまとめて、私がどのようなエンジニアなのかなるべく詳細にわかるようなサイトを目指します。
          興味を持っていただいた方は、公開しているアカウントよりコンタクトを取っていただけると転げ回って喜びます。
        </P>
        <p>
          みなさまどうかごゆっくりしていってください。
        </P>
      </div>
    </div>
    <div class="block block-three">
      <div>
        <h2><span class="title_one">P</span>rofile</h2>
        <p>
          プロフィールを記載する
        </P>
      </div>
    </div>
    <div class="block block-four">
      <div>
        <h2><span class="title_one">T</span>able of contents</h2>
        <v-card
          v-for="(content, i) in contents"
          :key="i"
          :to="content.to"
          class="mx-auto"
          max-width="400"
        >
          <v-img
            :src="content.image"
            class="white--text align-end"
            height="150px"
          >
            <v-card-title>{{ content.title }}</v-card-title>
          </v-img>
        </v-card>
      </div>
    </div>
    <div class="block block-five">
      <div>
        <h2><span class="title_one">C</span>areer</h2>
        <p>
          経歴をはる
        </P>
      </div>
    </div>
  </div>
</template>
<script>
import { VueTyper } from 'vue-typer'
export default {
  layout: 'top',
  components: {
    VueTyper
  },
  data () {
    return {
      contents: [
        {
          image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
          title: 'Skill',
          to: '/skill'
        },
        {
          image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
          title: 'Contents',
          to: '/contents'
        },
        {
          image: 'https://cdn.vuetifyjs.com/images/cards/docks.jpg',
          title: 'Accounts',
          to: '/accounts'
        }
      ]
    }
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

h2 {
  font-size: 60px;
}

p {
  font-size: 30px;
}

.title_one {
  font-size: 80px;
  color:yellow;
  font-weight: bold;
}

.inpact {
  color:yellow;
  font-weight: bold;
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
  background-image: url("/images/amanogawa.jpg");
  color: #ffffff;
  z-index: 110;
}

.block-three {
  background: #212E32;
  color: #fff;
  z-index: 120;
}
.block-four {
  background: #ffffff;
  z-index: 130;
}
.block-five {
  background: #212E32;
  color: #fff;
  z-index: 140;
}
</style>
