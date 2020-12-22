<template>
  <v-row>
    <v-col cols="12" id="profile" class="my-12">
      <transition name="slide-fade">
        <v-card v-if="visible" color="grey lighten-2" flat>
          <v-card-text class="pb-0 text-center">Profile</v-card-text>
          <v-card-text class="py-0 text-center headline font-weight-bold"
            ><span class="menu">自己紹介</span></v-card-text
          >

          <v-row class="mx-auto">
            <v-spacer></v-spacer>
            <v-col cols="10" sm="4" align-self="center">
              <v-img :src="image_src" />
            </v-col>
            <v-spacer></v-spacer>

            <v-col cols="12" sm="6" class="py-0 px-0">
              <v-card-text class="x-auto">
                <p
                  v-for="profile_list in profile_lists"
                  :key="profile_list.item"
                >
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
      </transition>
    </v-col>

    <v-col cols="12" id="background" class="my-12">
      <FadeIn>
        <v-card v-if="visible" color="#e5f6ff" flat>
          <v-card-text class="pb-0 text-center">Background</v-card-text>
          <v-card-text class="py-0 text-center headline font-weight-bold"
            ><span class="menu">経歴</span></v-card-text
          >

          <v-col cols="12" class="px-0">
            <v-timeline dense>
              <v-timeline-item
                v-for="(yearMonth, index) in yearMonths"
                :color="yearMonth.color"
                :key="`${index}-${yearMonth.yearMonth}`"
                small
              >
                <v-card
                  class="elevation-8"
                  :class="{ 'mr-12': !$vuetify.breakpoint.xs }"
                >
                  <v-card-title
                    :class="`font-weight-bold ${yearMonth.color}--text`"
                    >{{ yearMonth.yearMonth }}<br />
                    {{ yearMonth.title }}</v-card-title
                  >
                  <v-card-text
                    v-html="yearMonth.text"
                    class="black--text"
                    :class="{ 'pr-0': $vuetify.breakpoint.xs }"
                  >
                  </v-card-text>
                </v-card>
              </v-timeline-item>
            </v-timeline>
          </v-col>
        </v-card>
      </FadeIn>
    </v-col>

    <v-col cols="12" id="skills" class="my-12">
      <FadeIn>
        <v-card color="grey lighten-2" flat>
          <v-card-text class="pb-0 text-center">Skills</v-card-text>
          <v-card-text class="py-0 text-center headline font-weight-bold"
            ><span class="menu">習得した技術</span></v-card-text
          >

          <v-container class="px-0">
            <v-row justify="center">
              <v-card
                v-for="firstSkill in firstSkills"
                :key="firstSkill.name"
                class="text-center sheet"
                color="grey lighten-2"
                flat
              >
                <v-container>
                  <img class="img" :src="firstSkill.src" />
                  <h3 class="my-3">{{ firstSkill.name }}</h3>
                </v-container>
              </v-card>
            </v-row>

            <v-row justify="center">
              <v-card
                v-for="secondSkill in secondSkills"
                :key="secondSkill.name"
                class="text-center sheet"
                color="grey lighten-2"
                flat
              >
                <v-container>
                  <img class="img" :src="secondSkill.src" />
                  <h3 class="my-3">{{ secondSkill.name }}</h3>
                </v-container>
              </v-card>
            </v-row>
          </v-container>
        </v-card>
      </FadeIn>
    </v-col>

    <v-col cols="12" id="first-work" class="my-12">
      <FadeIn>
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
      </FadeIn>
    </v-col>

    <v-col cols="12" id="second-work" class="my-12">
      <FadeIn>
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
      </FadeIn>
    </v-col>
  </v-row>
</template>

<script>
export default {
  data() {
    return {
      visible: false,
      image_src: require('~/assets/football.jpg'),
      firstSkills: [
        {
          src: require('~/assets/images/skills/html-5.svg'),
          name: 'HTML',
        },
        {
          src: require('~/assets/images/skills/css-3.svg'),
          name: 'CSS',
        },
        {
          src: require('~/assets/images/skills/javascript.svg'),
          name: 'JavaScript',
        },
        {
          src: require('~/assets/images/skills/typescript.svg'),
          name: 'TypeScript',
        },
      ],
      secondSkills: [
        {
          src: require('~/assets/images/skills/vuejs.svg'),
          name: 'Vue.js',
        },
        {
          src: require('~/assets/images/skills/vuetifyjs.svg'),
          name: 'Vuetify.js',
        },
        {
          src: require('~/assets/images/skills/nuxtjs.svg'),
          name: 'Nuxt.js',
        },
        {
          src: require('~/assets/images/skills/firebase.svg'),
          name: 'Firebase',
        },
      ],
      profile_lists: [
        {
          item: '氏名',
          content: '島上 翔（しまがみ つばさ）',
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
        {
          item: '資格',
          content: '珠算検定1級、暗算検定準初段',
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
          text:
            '部活動はアメリカンフットボール部に入っていましたが、勉学に励むために途中で退部しました。そのおかげもあったか自分が志望していた大学に入学することが出来ました。',
        },
        {
          yearMonth: '2015/4',
          color: 'blue',
          title: '関西外国語大学　入学',
          text:
            '大学では英語とスペイン語を主に勉強していました。サークル活動とアルバイトを両立することが難しいと考えたので、サークルには入らずアルバイトだけに専念することにしました。',
        },
        {
          yearMonth: '2015/4',
          color: 'orange',
          title: 'ファロス個別指導学院　入社（アルバイト）',
        },
        {
          yearMonth: '2018/3',
          color: 'green',
          title: '関西外国語大学　中退',
          text:
            '周囲となじむことが出来なかったり、将来自分が本当にやってみたいことを考えた時に今の環境では実現できないと思い退学しました。<br>退学後、アルバイトをしながら自分の進退について考えた時にサイトやアプリを作ることが面白そうだなと思い、少しずつプログラミングの勉強をするようになりました。<br>幸運にも英語等の外国語を勉強していたこともあってか、取っつきやすく感じました。',
        },
        {
          yearMonth: '2020/7',
          color: 'purple',
          title: 'ファロス個別指導学院　退社',
          text:
            '退社を決意した一番の理由は、本格的に就職活動がしたいと思ったからです。退社前からプログラミングの勉強を少ししていましたが、中途半端にしかやってこずあまり身についていないと思いました。<br>アルバイトでは授業を主に行っていましたが他の講師が書いた授業カルテを添削する業務も任されていました。誤字、脱字や内容の不備がないか確認をしていました。<br>授業でも生徒が解いている様子を見てどこが間違っているのか、なぜ間違っているのかを生徒に伝わるように指摘したりもしていました。その経験を通じて普段から細部まで気にするようになりました。<br>プログラミングでも、自分が書いたコードに間違いがないかどうかをよく確認するようになりました。エンジニアとして必要なスキルを習得出来たと思っているので、今後エンジニアとしての仕事でもこの経験を生かしていきたいと思います。',
        },
      ],
      work_1: {
        title: '「ソートアプリ」',
        contain: `自分の好きなメンバーを選んでソートが出来るアプリです。`,
        video: require('~/assets/videos/work-1.mp4'),
        github: 'https://github.com/xyytgae/sakamichi-sort',
        deploy: 'https://sakamichi-sort.web.app/',
      },
      work_2: {
        title: '「モルックのスコア記録アプリ」',
        contain: `モルックのスコアを記録するためのアプリです。`,
        video: require('~/assets/videos/work-2.mp4'),
        github: 'https://github.com/xyytgae/my-molkky',
        deploy: 'https://my-molkky.web.app',
      },
    }
  },
  mounted() {
    this.visible = true
  },
}
</script>

<style lang="scss" scoped>
.menu {
  font-size: 2rem !important;
  background: linear-gradient(transparent 90%, pink 50%);
}

.sheet {
  @media screen and (max-width: 1200px) {
    width: 150px;
  }
  width: 200px;
}

.img {
  width: 100%;
  height: auto;
}

.video {
  width: 90%;
  height: auto;
}

h4 {
  margin-bottom: 25px;
}

.work_describe {
  font-size: 16px;
  margin-bottom: 15px;
}
</style>
