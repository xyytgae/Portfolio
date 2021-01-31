<template>
  <v-card color="grey lighten-2" flat>
    <v-card-text class="pb-0 text-center">Profile</v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold"
      ><span class="menu">自己紹介</span></v-card-text
    >

    <v-row class="mx-auto">
      <v-spacer></v-spacer>
      <v-col cols="10" sm="4" align-self="center">
        <img class="img" :src="image_src" />
      </v-col>
      <v-spacer></v-spacer>

      <v-col cols="12" sm="6" class="py-0 px-0">
        <v-card-text class="x-auto">
          <p v-for="profile_list in profile_lists" :key="profile_list.item">
            <span> {{ profile_list.item }}：</span>
            <span>{{ profile_list.content }} </span>
          </p>

          <div>
            <v-btn
              v-for="profile_link_list in profile_link_lists"
              :key="profile_link_list.item"
              :href="profile_link_list.link"
              target="_blank"
              rel="nooopener noreferrer"
              class="mr-2 text-none px-2"
            >
              <img :src="profile_link_list.icon" class="mr-1 icon" />{{
                profile_link_list.item
              }}</v-btn
            >
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
      image_src: require("~/assets/football.jpg"),
      profile_lists: [
        {
          item: "氏名",
          content: "島上 翔（しまがみ つばさ）"
        },
        {
          item: "生年月日",
          content: "1997年3月31日（23歳）"
        },
        {
          item: "性別",
          content: "男"
        },
        {
          item: "趣味",
          content: "サッカー観戦"
        },
        {
          item: "資格",
          content: "珠算検定1級、暗算検定準初段"
        }
      ],
      profile_link_lists: [
        {
          item: "Github",
          link: "https://github.com/xyytgae",
          icon: require("~/assets/images/link_icons/github.png")
        },
        {
          item: "Twitter",
          link: "https://twitter.com/wing_1008",
          icon: require("~/assets/images/link_icons/twitter.png")
        },
        {
          item: "Qiita",
          link: "https://qiita.com/Shimagami",
          icon: require("~/assets/images/link_icons/qiita.png")
        }
      ]
    };
  }
};
</script>

<style scoped>
.icon {
  height: 24px;
  width: auto;
}
</style>
