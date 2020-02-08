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
        class="headline font-italic font-weight-medium"
      />
    </div>
    <div class="block block-two">
      <div>
        <h2 class="display-3 font-weight-black">
          <span class="inpact">A</span>bout this site
        </h2>
        <br>
        <p class="headline font-weight-black">
          このサイトは、<span class="inpact">圧倒的成長</span>と<span class="inpact">楽しく働くこと</span>を追求するいとあきのポートフォリオです。
          普段のアウトプットや、アカウントなどをまとめて、私がどのようなエンジニアなのかなるべく詳細にわかるようなサイトを目指します。
          興味を持っていただいた方は、公開しているアカウントよりコンタクトを取っていただけると転げ回って喜びます。
        </P>
        <p class="headline font-weight-black">
          みなさまどうかごゆっくりしていってください。
        </P>
      </div>
    </div>
    <div class="block block-three">
      <div>
        <h2 class="display-3 font-weight-black">
          <span class="inpact">P</span>rofile
        </h2>
        <v-row justify="center">
          <v-col
            cols="12"
            sm="10"
            md="6"
            lg="6"
          >
            <v-avatar
              class="profile"
              color="grey"
              size="300"
              tile
            >
              <v-img src="/images/profile.jpg" />
            </v-avatar>
          </v-col>
          <v-col
            cols="12"
            sm="10"
            md="6"
            lg="6"
          >
            <v-simple-table
              v-if="$vuetify.breakpoint.xs || $vuetify.breakpoint.sm"
              dense
            >
              <template v-slot:default>
                <tbody>
                  <tr v-for="item in introduction" :key="item.name">
                    <td>{{ item.name }}</td>
                    <td>{{ item.value }}</td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
            <v-simple-table
              v-if="$vuetify.breakpoint.md || $vuetify.breakpoint.lg"
            >
              <template v-slot:default>
                <tbody>
                  <tr v-for="item in introduction" :key="item.name">
                    <td>{{ item.name }}</td>
                    <td>{{ item.value }}</td>
                  </tr>
                </tbody>
              </template>
            </v-simple-table>
          </v-col>
        </v-row>
      </div>
    </div>
    <div class="block block-four">
      <div>
        <h2 class="display-3 font-weight-black">
          <span class="inpact">T</span>able of contents
        </h2>
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
        <h2 class="display-3 font-weight-black">
          <span class="inpact">C</span>areer
        </h2>
        <p>
          作成中
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
      ],
      introduction: [
        {
          name: 'Name：',
          value: 'Ito Akihiro'
        },
        {
          name: 'Birthday',
          value: '1989/04/17 (Aries)'
        },
        {
          name: 'Blood Type',
          value: 'O型'
        },
        {
          name: 'motto',
          value: '困難の中に機会がある(アインシュタイン)'
        },
        {
          name: 'respected',
          value: '堀江 貴文、与沢 翼'
        },
        {
          name: 'Hobby',
          value: 'アマプラ、筋トレ、野球、時々サバゲー'
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
  background: #f5f5f5;
}

.inpact {
  color: #ffd700;
  font-weight: bold;
}

.block-one {
  z-index: 100;
}

.block-two {
  background-image: url("/images/amanogawa.jpg");
  color: #ffffff;
  z-index: 110;
}

.block-three {
  background: #f5f5f5;
  color: #808080;
  z-index: 120;
}

.block-four {
  background: #292961;
  color: #808080;
  z-index: 130;
}

.block-five {
  background: #212E32;
  color: #fff;
  z-index: 140;
}
</style>
