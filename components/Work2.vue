<template>
  <v-card color="grey lighten-2" flat>
    <v-card-text class="pb-0 text-center">
      Work#2
    </v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold"
      ><span class="menu">{{ work_2.title }}</span></v-card-text
    >

    <v-row>
      <v-col cols="12" md="6" class="text-center align-self-center">
        <video class="video" :src="work_2.video" controls></video>
      </v-col>
      <v-col cols="12" md="6">
        <v-card-text>
          <div class="work_describe">
            【概要】<br />
            モルックというボウリングに似たスポーツのスコアを記録するアプリです。<br />
            <a
              target="_blank"
              ref="noopener noreferrer"
              href="https://molkky.jp/molkky/"
              >詳しいルールはこちらです。</a
            >(引用：日本モルック協会公式サイト)
            <br />
            簡単に説明すると、モルックという木の棒を投げ50点ちょうどになるように、スコアを積み重ねていくスポーツです。<br />
            Github：
            <a
              target="_blank"
              ref="noopener noreferrer"
              :href="work_2.github"
              >{{ work_2.github }}</a
            >
            <br />
            デプロイ：<a
              target="_blank"
              ref="noopener noreferrer"
              :href="work_2.deploy"
              >{{ work_2.deploy }}</a
            >
          </div>

          <div class="work_describe">
            【開発環境】
            <ul>
              <li>
                Nuxt.js
              </li>
              <li>
                Vuetify.js
              </li>
              <li>
                Firebase
              </li>
            </ul>
          </div>

          <div class="work_describe">
            【内容】<br />
            公式スコアアプリが既にあるのですが、それは自分で他のプレイヤーも含めたスコアを記録することになります。<br />
            それでは少し不便だと感じ、動画のように自分のスコアだけを入力するだけでリアルタイムで全員のスコアを確認出来るようにアプリを作りました。<br />
          </div>

          <div class="work_describe">
            【ポイント】
            <ul>
              <li>現在ある部屋や、全員のスコアをリアルタイムで表示</li>
              <li>初めて使うユーザーにもわかるよう、進行状況を表示</li>
              <li>UIにはVuetify.jsを採用</li>
            </ul>
          </div>
        </v-card-text>
      </v-col>
    </v-row>
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      work_2: {
        title: '「モルックのスコア記録アプリ」',
        contain: `モルックのスコアを記録するためのアプリです。`,
        video: require('~/assets/videos/work-2.mp4'),
        github: 'https://github.com/xyytgae/my-molkky',
        deploy: 'https://my-molkky.web.app',
      },
    }
  },
}
</script>
