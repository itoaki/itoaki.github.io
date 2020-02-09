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
        <v-spacer />
        <v-row dense justify="center">
          <v-col
            v-for="(content, i) in contents"
            :key="i"
            cols="12"
            sm="12"
            md="4"
            lg="4"
          >
            <v-card
              :to="content.to"
              class="mx-auto"
              max-width="400"
            >
              <v-img
                :src="content.image"
                class="grey--text text--darken-3 align-end"
                height="150px"
              >
                <v-card-title
                  class="display-1 font-weight-bold"
                >
                  {{ content.title }}
                </v-card-title>
              </v-img>
              <v-card-subtitle
                v-if="$vuetify.breakpoint.md || $vuetify.breakpoint.lg"
                class="pb-0"
              >
                {{ content.subtitle }}
              </v-card-subtitle>
              <v-card-text
                v-if="$vuetify.breakpoint.md || $vuetify.breakpoint.lg"
                class="text--primary"
              >
                <div>{{ content.text }}</div>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </div>
    </div>
    <div class="block-five">
      <div>
        <h2 class="display-3 font-weight-black">
          <span class="inpact">C</span>areer
        </h2>
        <v-timeline>
          <v-timeline-item
            v-for="(carrer, i) in carrers"
            :key="i"
            :color="carrer.color"
            small
          >
            <template v-slot:opposite>
              <span
                :class="`headline font-weight-bold ${carrer.color}--text`"
                v-text="carrer.year"
              />
            </template>
            <div class="py-4">
              <h2 :class="`headline font-weight-light mb-4 ${carrer.color}--text`">
                {{ carrer.event }}
              </h2>
              <div>
                {{ carrer.text }}
              </div>
            </div>
          </v-timeline-item>
        </v-timeline>
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
          image: '/images/triangle.jpg',
          title: 'Skill',
          to: '/skill',
          subtitle: '目指せフルスタック！',
          text: 'ページがごちゃったときずいた時、また１つ違う景色が見えるはずっ！'
        },
        {
          image: '/images/circle.jpg',
          title: 'Contents',
          to: '/contents',
          subtitle: '今までの軌跡',
          text: 'ページに収まりきらないほどのたくさんのものを作りたいっ♪'
        },
        {
          image: '/images/squere.jpg',
          title: 'Accounts',
          to: '/accounts',
          subtitle: '放置してたらすみません',
          text: 'エンジニアの方も、そうじゃない方も、友達になれたら嬉しいです。気軽に絡んでくださいっ☆'
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
      ],
      carrers: [
        {
          color: 'cyan',
          year: '2012',
          event: '大学卒業・就職',
          text: '千葉県の理系大学を卒業しました。独立系SIerに就職してエンジニアデビューしました。'
        },
        {
          color: 'green',
          year: '2016/04',
          event: '40億円ウォーターフォールプロジェクトに挑戦！',
          text: '体力のある今のうちに経験しておこうと思い、部署移動を願い出てアサインされました。設計、開発、仕様変更対応、パフォーマンスチューニングなど様々な経験ができたのと、つよつよマネジメント層の仕事を間近で見て学ぶことができた。人生の思い出深いプロジェクトの1つ'
        },
        {
          color: 'pink',
          year: '2017/11',
          event: 'サービス開発を始める',
          text: '自社サービス開発をしている部署に移動しました。ここでは主にscrum開発、scrumマスター見習い、HRTech、1on1など、技術以外の部分で学ぶことが多かった。'
        },
        {
          color: 'amber',
          year: '2019/05',
          event: '転職',
          text: 'サービス開発が楽しすぎて、もっと色々な経験が積みたくなって、転職を決意。toCもできる、大規模サービスを提供している事業会社に転職しました。'
        },
        {
          color: 'orange',
          year: 'now / feature',
          event: '今とこれから',
          text: '今を楽しく生きてます。今後、どんな役割をになっていくか分からないけど、ずっと物作りに関わっていきたい。ずっとプログラムは書いていたいと思ってます。'
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
  color: #808080;
}

.inpact {
  color: #ffd700;
  font-weight: bold;
}

.block-one {
  z-index: 100;
}

.block-two {
  background-size: cover;
  background-image: url("/images/background.jpg");
  color: #ffffff;
  z-index: 110;
}

.block-three {
  background: #f5f5f5;
  z-index: 120;
}

.block-four {
  background-size: cover;
  background-image: url("/images/background2.png");
  z-index: 130;
}

.block-five {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: center;
  position: -webkit-sticky;
  position: sticky;
  top: 0;
  background: #f5f5f5;
  background: #212E32;
  color: #ffffff;
  z-index: 140;
}
</style>
