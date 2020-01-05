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
            cols="12"
            sm="12"
            md="6"
            lg="6"
          >
            <v-card
              :href="card.href"
              link
              target="_blank"
            >
              <div class="d-flex flex-no-wrap justify-space-between">
                <div>
                  <v-card-title
                    v-text="card.title"
                    class="headline"
                  />
                  <v-card-subtitle>subtitle</v-card-subtitle>
                </div>
                <v-avatar
                  class="ma-3"
                  size="125"
                  tile
                >
                  <v-img :src="card.src" />
                </v-avatar>
              </div>
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
          src: '/itoaki.github.io/logos/octocat.png',
          href: 'https://github.com/itoaki',
          flex: 6
        },
        {
          title: 'GitLab',
          src: '/itoaki.github.io/logos/gitlab.svg',
          href: 'https://gitlab.com/Itoaki',
          flex: 6
        },
        {
          title: 'はてなブログ',
          src: '/itoaki.github.io/logos/hatenablog.svg',
          href: 'https://techstation.hatenablog.com/',
          flex: 6
        },
        {
          title: 'note',
          src: '/itoaki.github.io/logos/note.svg',
          href: 'https://note.com/itoaki0417',
          flex: 6
        },
        {
          title: 'Qiita',
          src: '/itoaki.github.io/logos/qiita.png',
          href: 'https://qiita.com/itoaki0417',
          flex: 6
        },
        {
          title: 'Twitter',
          src: '/itoaki.github.io/logos/twitter.svg',
          href: 'https://twitter.com/itoaki0417',
          flex: 6
        },
        {
          title: 'Wantedly',
          src: '/itoaki.github.io/logos/wantedly.svg',
          href: 'https://www.wantedly.com/users/127449944',
          flex: 6
        },
        {
          title: 'Linkedin',
          src: '/itoaki.github.io/logos/linkedin.png',
          href: 'https://www.linkedin.com/in/akihiro-ito-042319116',
          flex: 6
        }
      ]
    }
  }
}
</script>
