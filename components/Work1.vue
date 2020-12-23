<template>
  <v-card color="#e5f6ff" flat>
    <v-card-text class="pb-0 text-center">
      Work#1
    </v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold">
      <span class="menu">
        {{ work_1.title }}
      </span>
    </v-card-text>

    <v-row>
      <v-col cols="12" md="6" class="text-center align-self-center px-0">
        <video class="video" :src="work_1.video" controls></video>
      </v-col>
      <v-col class="px-0" cols="12" md="6">
        <v-card-text>
          <div class="work_describe">
            【概要】<br />
            坂道グループから自分の好きなメンバーを選んで、ポイント順にソートしてくれるアプリです。<br />
            Github：
            <a
              target="_blank"
              ref="noopener noreferrer"
              :href="work_1.github"
              >{{ work_1.github }}</a
            >
            <br />
            デプロイ：<a
              target="_blank"
              ref="noopener noreferrer"
              :href="work_1.deploy"
              >{{ work_1.deploy }}</a
            >
          </div>

          <div class="work_describe">
            【開発環境】
            <ul>
              <li>Vue.js</li>
              <li>Vuetify.js</li>
              <li>Firebase（ホスティングのみ）</li>
            </ul>
          </div>

          <div class="work_describe">
            【内容】<br />
            使い方は最初にソートしたいグループを選択後、ソートしたいメンバーを選択します。<br />
            選択したメンバーが2人ずつ表示されるので、自分の好きな方を選んでいき全ての組み合わせが終了次第、結果が表示されます。<br />
            類似したアプリは多々ありますが、自分のソートしたいメンバーを最初に選ぶ事が出来るものがなかったのでこのアプリを作ることにしました。<br />
          </div>

          <div class="work_describe">
            【ポイント】
            <ul>
              <li>
                選択中のグループが分かりやすいよう、サイト全体のカラーを動的に変化
              </li>
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
      work_1: {
        title: '「ソートアプリ」',
        contain: `自分の好きなメンバーを選んでソートが出来るアプリです。`,
        video: require('~/assets/videos/work-1.mp4'),
        github: 'https://github.com/xyytgae/sakamichi-sort',
        deploy: 'https://sakamichi-sort.web.app/',
      },
    }
  },
}
</script>
