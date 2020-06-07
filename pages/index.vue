<template>
  <v-layout
    column
    justify-center
    align-center
  >
    <v-container>
      <v-row dense justify="center">
        <v-col
          cols="12"
          sm="10"
          md="12"
          lg="12"
        >
          <v-card color="#292961" dark>
            <v-card-title>Account List</v-card-title>
          </v-card>
        </v-col>
      </v-row>
      <v-row dense justify="center">
        <v-col
          v-for="card in cards"
          :key="card.title"
          cols="12"
          sm="10"
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
                <v-card-title v-text="card.title" />
                <v-card-subtitle v-text="card.subtitle" />
              </div>
              <v-avatar
                class="ma-3"
                size="125"
                tile
              >
                <v-img :src="card.src" contain />
              </v-avatar>
            </div>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </v-layout>
</template>

<script>
export default {
  data () {
    return {
      cards: [
        {
          title: 'GitHub',
          subtitle: 'GitHubのアカウントです。',
          src: '/logos/octocat.png',
          href: 'https://github.com/itoaki'
        },
        {
          title: 'GitLab',
          subtitle: 'GitLabのアカウントです。',
          src: '/logos/gitlab.svg',
          href: 'https://gitlab.com/Itoaki'
        },
        {
          title: 'はてなブログ',
          subtitle: '勉強したことをなんでも書いてます。',
          src: '/logos/hatenablog.svg',
          href: 'https://techstation.hatenablog.com/'
        },
        {
          title: 'note',
          subtitle: '普段考えていることなどを書いてます。',
          src: '/logos/note.svg',
          href: 'https://note.com/itoaki0417'
        },
        {
          title: 'Qiita',
          subtitle: '作成したもののまとめ記事を書いてます。',
          src: '/logos/qiita.png',
          href: 'https://qiita.com/itoaki0417'
        },
        {
          title: 'Twitter',
          subtitle: 'お気軽にフォローしてください。',
          src: '/logos/twitter.svg',
          href: 'https://twitter.com/itoaki0417'
        },
        {
          title: 'Wantedly',
          subtitle: 'プロフィール鋭意記載中',
          src: '/logos/wantedly.svg',
          href: 'https://www.wantedly.com/users/127449944'
        },
        {
          title: 'Linkedin',
          subtitle: 'お友達になりましょう。',
          src: '/logos/linkedin.png',
          href: 'https://www.linkedin.com/in/akihiro-ito-042319116'
        }
      ]
    }
  }
}
</script>
