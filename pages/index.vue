<template>
  <v-row>
    <v-col cols="12">
      <v-card id="profile">
        <v-card-title class="headline">プロフィール</v-card-title>

        <v-row>
          <v-col cols="4" align-self="center">
            <v-img :src="image_src" />
          </v-col>

          <v-col cols="6">
            <v-card-text>
              <v-row> </v-row>
              <p v-for="profile_list in profile_lists" :key="profile_list.item">
                <span> {{ profile_list.item }}：</span>
                <span>{{ profile_list.content }} </span>
              </p>

              <p
                v-for="profile_link_list in profile_link_lists"
                :key="profile_link_list.item"
              >
                <span>{{ profile_link_list.item }}：</span>
                <a :href="profile_link_list.link">{{
                  profile_link_list.content
                }}</a>
              </p>
            </v-card-text>
          </v-col>
        </v-row>
      </v-card>
    </v-col>

    <v-col cols="12" id="background">
      <v-card class="grey lighten-2">
        <v-card-title class="headline">経歴</v-card-title>

        <!-- <v-card color="grey"> -->
        <v-row justify="center">
          <v-col cols="10">
            <v-timeline class="px-5">
              <v-timeline-item
                v-for="(yearMonth, index) in yearMonths"
                :color="yearMonth.color"
                :key="`${index}-${yearMonth.yearMonth}`"
              >
                <template v-slot:opposite>
                  <span>
                    {{ yearMonth.yearMonth }}
                  </span>
                </template>

                <v-card>
                  <v-card-title>{{ yearMonth.title }}</v-card-title>
                  <v-card-text>
                    {{ yearMonth.text }}
                  </v-card-text>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </v-col>
        </v-row>
        <!-- </v-card> -->
      </v-card>
    </v-col>

    <v-col cols="12" id="languages">
      <v-card>
        <v-card-title class="headline">学習している言語</v-card-title>
        <v-row justify="center">
          <v-col
            cols="2"
            class="text-center"
            v-for="firstImage in firstImages"
            :key="firstImage.name"
          >
            <img :src="firstImage.src" height="150" width="150" />
            <h3 class="my-3">{{ firstImage.name }}</h3>
          </v-col>
        </v-row>

        <v-row justify="center">
          <v-col
            cols="2"
            class="text-center"
            v-for="secondImage in secondImages"
            :key="secondImage.name"
          >
            <img :src="secondImage.src" height="150" width="150" />
            <h3 class="my-3">{{ secondImage.name }}</h3>
          </v-col>
        </v-row>
      </v-card>
    </v-col>

    <v-col cols="12" id="first-work">
      <v-card class="grey lighten-2">
        <v-card-title class="headline">{{ work_1.title }}</v-card-title>
        <v-row>
          <v-col cols="6">
            <v-card-text>
              <h4>
                【概要】<br />
                坂道グループから自分の好きなメンバーを選んで、ポイント順にソートしてくれるアプリです。
              </h4>

              <h4>
                【開発環境】
                <ul>
                  <li>Vue.js</li>
                  <li>Vuetify.js</li>
                  <li>Firebase（ホスティングのみ）</li>
                </ul>
              </h4>

              <h4>
                【内容】<br />
                使い方は最初にソートしたいグループを選択後、ソートしたいメンバーを選択します。<br />
                選択したメンバーが2人ずつ表示されるので、自分の好きな方を選んでいき全ての組み合わせが終了次第、結果が表示されます。<br />
                類似したアプリは多々ありますが、自分のソートしたいメンバーを最初に選ぶ事が出来るものがなかったのでこのアプリを作ることにしました。<br />
              </h4>

              <h4>
                【ポイント】
                <ul>
                  <li>
                    選択中のグループが分かりやすいよう、サイト全体のカラーを動的に変化
                  </li>
                  <li>UIにはVuetify.jsを採用</li>
                </ul>
              </h4>
            </v-card-text>
          </v-col>
          <v-col cols="6" class="text-center align-self-center">
            <video class="video" :src="work_1.video" controls></video>
          </v-col>
        </v-row>
      </v-card>
    </v-col>

    <v-col cols="12" id="second-work">
      <v-card>
        <v-card-title class="headline">{{ work_2.title }}</v-card-title>
        <v-row>
          <v-col cols="6">
            <v-card-text>
              <h4>
                【概要】<br />
                モルックというボウリングに似たスポーツのスコアを記録するアプリです。<br />
                簡単に説明すると、モルックという木の棒を投げ50点ちょうどになるように、スコアを積み重ねていくスポーツです。<br />
                <a target="_blank" href="https://molkky.jp/molkky/"
                  >詳しいルールはこちらです。</a
                >(引用：日本モルック協会公式サイト)
              </h4>

              <h4>
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
              </h4>

              <h4>
                【内容】<br />
                公式スコアアプリが既にあるのですが、それは自分で他のプレイヤーも含めたスコアを記録することになります。<br />
                それでは少し不便だと感じ、動画のように自分のスコアだけを入力するだけでリアルタイムで全員のスコアを確認出来るようにアプリを作りました。<br />
              </h4>

              <h4>
                【ポイント】
                <ul>
                  <li>現在ある部屋や、全員のスコアをリアルタイムで表示</li>
                  <li>初めて使うユーザーにもわかるよう、進行状況を表示</li>
                  <li>UIにはVuetify.jsを採用</li>
                </ul>
              </h4>
            </v-card-text>
          </v-col>

          <v-col cols="6" class="text-center align-self-center">
            <video class="video" :src="work_2.video" controls></video>
          </v-col>
        </v-row>
      </v-card>
    </v-col>
  </v-row>
</template>

<script>
export default {
  components: {},
  data() {
    return {
      image_src: require('~/assets/football.jpg'),
      firstImages: [
        {
          src: require('~/assets/html-5.svg'),
          name: 'HTML',
        },
        {
          src: require('~/assets/css-3.svg'),
          name: 'CSS',
        },
        {
          src: require('~/assets/javascript.svg'),
          name: 'JavaScript',
        },
      ],
      secondImages: [
        {
          src: require('~/assets/vue.svg'),
          name: 'Vue.js',
        },
        {
          src: require('~/assets/vuetifyjs.svg'),
          name: 'Vuetify.js',
        },
        {
          src: require('~/assets/nuxt-icon.svg'),
          name: 'Nuxt.js',
        },
        {
          src: require('~/assets/firebase.svg'),
          name: 'Firebase',
        },
      ],
      profile_lists: [
        {
          item: '氏名',
          content: '島上　翔（しまがみ　つばさ）',
        },
        {
          item: '生年月日',
          content: '1997年3月31日（23歳）',
        },
        {
          item: '性別',
          content: '男',
        },
        {
          item: '趣味',
          content: 'サッカー観戦',
        },
      ],
      profile_link_lists: [
        {
          item: 'Contact',
          content: 'Email',
          link: 'mailto:xyytgae@gmail.com',
        },
        {
          item: 'Github',
          content: 'xyytgae',
          link: 'https://github.com/xyytgae',
        },
      ],
      yearMonths: [
        {
          yearMonth: '2015/3',
          color: 'red',
          title: '近畿大学附属高等学校　卒業',
        },
        {
          yearMonth: '2015/4',
          color: 'blue',
          title: '関西外国語大学　入学',
        },
        {
          yearMonth: '2015/4',
          color: 'orange',
          title: 'ファロス個別指導学院　入社（アルバイト）',
          text:
            '興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。',
        },
        {
          yearMonth: '2018/3',
          color: 'green',
          title: '関西外国語大学　中退',
          text:
            '理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。',
        },
        {
          yearMonth: '2020/7',
          color: 'black',
          title: 'ファロス個別指導学院退社',
          text:
            '理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。理由は～だから。',
        },
      ],
      work_1: {
        title: '作品#1「ソートアプリ」',
        contain: `自分の好きなメンバーを選んでソートが出来るアプリです。`,
        video: require('~/assets/videos/work-1.mp4'),
      },
      work_2: {
        title: '作品#2「モルックのスコア記録アプリ」',
        contain: `モルックのスコアを記録するためのアプリです。`,
        video: require('~/assets/videos/work-2.mp4'),
      },
    }
  },
}
</script>

<style scoped>
.video {
  width: 90%;
  height: 90%;
}

h4 {
  margin-bottom: 25px;
}
</style>
