<template>
  <v-card color="#e5f6ff" flat>
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
            class="elevation-4"
            :class="{ 'mr-12': !$vuetify.breakpoint.xs }"
          >
            <v-card-title :class="`font-weight-bold ${yearMonth.color}--text`"
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
</template>

<script>
export default {
  data() {
    return {
      yearMonths: [
        {
          yearMonth: '2015/3',
          color: 'red',
          title: '近畿大学附属高等学校　卒業',
          text:
            '部活動はアメリカンフットボール部に入っていましたが、勉学に励むために途中で退部しました。そのおかげもあって自分が志望していた大学に入学することが出来ました。',
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
    }
  },
}
</script>
