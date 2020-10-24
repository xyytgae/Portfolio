<template>
  <v-row>
    <v-col cols="12">
      <v-card>
        <v-card-title class="headline">Profile</v-card-title>

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

    <v-col cols="12">
      <v-card>
        <v-card-title class="headline">Background</v-card-title>

        <v-card color="grey">
          <v-row>
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
        </v-card>
      </v-card>
    </v-col>

    <v-col>
      <v-card>
        <v-card-title class="headline">学習している言語</v-card-title>
        <v-row justify="center" align="end">
          <v-col cols="2" class="text-center">
            <v-img :src="htmlImage_src" />
            <h3>HTML</h3>
          </v-col>
          <v-col cols="2" class="text-center">
            <v-img :src="cssImage_src" />
            <h3>CSS</h3>
          </v-col>

          <v-col cols="2" class="text-center">
            <v-img :src="javascriptImage_src" />
            <h3>JavaScript</h3>
          </v-col>
        </v-row>

        <v-row justify="center" align="start">
          <v-col cols="2" class="text-center">
            <v-img :src="vueImage_src" />
            <h3 class="mb-auto">Vue.js</h3>
          </v-col>
          <v-col cols="2" class="text-center">
            <v-img :src="nuxtImage_src" />
            <h3>Nuxt.js</h3>
          </v-col>
          <v-col cols="2" class="text-center">
            <v-img :src="vuetifyImage_src" />
            <h3>Vuetify</h3>
          </v-col>
          <v-col cols="2" class="text-center">
            <v-img :src="firebaseImage_src" />
            <h3>Firebase</h3>
          </v-col>
        </v-row>
      </v-card>
    </v-col>

    <v-col cols="12">
      <v-card>
        <v-card-title class="headline">作品#1</v-card-title>

        <v-card-text
          >作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。</v-card-text
        >
      </v-card>
    </v-col>

    <v-col cols="12">
      <v-card>
        <v-card-title class="headline">作品#2</v-card-title>

        <v-card-text
          >作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。作品の説明。</v-card-text
        >
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
      htmlImage_src: require('~/assets/html-5.svg'),
      cssImage_src: require('~/assets/css-3.svg'),
      javascriptImage_src: require('~/assets/javascript.svg'),
      vueImage_src: require('~/assets/vue.svg'),
      vuetifyImage_src: require('~/assets/vuetifyjs.svg'),
      nuxtImage_src: require('~/assets/nuxt-icon.svg'),
      firebaseImage_src: require('~/assets/firebase.svg'),
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
          title: 'ファロス個別指導学院入社（アルバイト）',
          text:
            '興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。興味があったから。',
        },
        {
          yearMonth: '2018/3',
          color: 'green',
        },
        {
          yearMonth: '2020/7',
          color: 'black',
        },
      ],
    }
  },
}
</script>

<style scoped></style>
