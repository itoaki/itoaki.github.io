<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-flex
      xs12
      sm8
      md6
    >
      <v-container fluid>
        <v-card color="#292961" dark>
          <v-card-title>
            Account List
          </v-card-title>
        </v-card>

        <v-row dense>
          <v-col
            v-for="card in cards"
            :key="card.title"
            :cols="card.flex"
          >
            <v-card
              :href="card.href"
              link
              target="_blank"
            >
              <v-img
                :src="card.src"
                class="white--text align-end"
                gradient="to bottom, rgba(0,0,0,.1), rgba(0,0,0,.5)"
                height="200px"
              >
                <v-card-title v-text="card.title" />
              </v-img>
              <v-card-text>
                <p>Vuetify is a progressive Material Design component framework for Vue.js. It was designed to empower developers to create amazing applications.</p>
              </v-card-text>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </v-flex>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      cards: [
        {
          title: 'GitHub',
          src: 'https://cdn.vuetifyjs.com/images/cards/house.jpg',
          href: 'https://github.com/itoaki',
          flex: 6
        },
        {
          title: 'GitLab',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://gitlab.com/Itoaki',
          flex: 6
        },
        {
          title: 'はてなブログ',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://techstation.hatenablog.com/',
          flex: 6
        },
        {
          title: 'note',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://note.com/itoaki0417',
          flex: 6
        },
        {
          title: 'Qiita',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://qiita.com/itoaki0417',
          flex: 6
        },
        {
          title: 'Twitter',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://twitter.com/itoaki0417',
          flex: 6
        },
        {
          title: 'Wantedly',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://www.wantedly.com/users/127449944',
          flex: 6
        },
        {
          title: 'Linkedin',
          src: 'https://cdn.vuetifyjs.com/images/cards/road.jpg',
          href: 'https://www.linkedin.com/in/akihiro-ito-042319116',
          flex: 6
        }
      ]
    }
  }
}
</script>
