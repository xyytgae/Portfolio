<template>
  <v-card color="#e5f6ff" flat>
    <v-card-text class="pb-0 text-center">Contact</v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold"
      ><span class="menu">お問い合わせ</span></v-card-text
    >

    <!-- 抜粋です -->
    <v-text-field v-model="name" label="お名前" required />
    <v-text-field v-model="email" label="メールアドレス" required />
    <v-text-field v-model="company" label="会社名（法人の方のみ）" />
    <v-textarea v-model="message" label="お問い合わせ内容" required />
    <v-text-field
      v-model="botfield"
      label="人間は入力しないでください"
      v-show="false"
    />
    <v-btn color="primary" @click="submit">送信</v-btn>

    <!-- <form name="contact" method="POST" netlify>
      <v-form ref="form" v-model="valid">

        <v-col cols="12" md="3">
          <v-text-field
            type="hidden"
            outlined
            shaped
            :rules="[required]"
            color="orange"
            v-model="form.name"
            label="なまえ"
          ></v-text-field>
        </v-col>
        <v-col cols="12" md="3">
          <v-text-field
            type="hidden"
            outlined
            shaped
            :rules="[required]"
            color="orange"
            v-model="form.email"
            label="Email"
          ></v-text-field>
        </v-col>
        <v-col cols="12" md="3">
          <v-text-field
            type="hidden"
            outlined
            shaped
            :rules="[required]"
            color="orange"
            v-model="form.title"
            label="件名"
          ></v-text-field>
        </v-col>

        <v-col cols="12" md="10">
          <v-textarea
            type="hidden"
            outlined
            shaped
            :rules="[required]"
            color="orange"
            v-model="form.contents"
            label="お問い合わせ内容"
          ></v-textarea>
        </v-col>

        <v-col class="text-center">
          <v-btn
            color="orange"
            :disabled="!valid || loading"
            :loading="loading"
            :dark="valid"
            x-large
            @click="send"
            >送信する</v-btn
          >
        </v-col>

        <v-col class="text-center">
          {{ message }}
        </v-col>

      </v-form>
    </form> -->
  </v-card>
</template>

<script>
export default {
  data() {
    return {
      name: '',
      email: '',
      company: '',
      message: '',
      botfield: '',
      // inputItems: [
      //   {
      //     name: '名前',
      //   },
      //   {
      //     name: 'Email',
      //   },
      //   {
      //     name: '件名',
      //   },
      // ],
      // form: {
      //   name: '',
      //   email: '',
      //   title: '',
      //   contents: '',
      // },
      // valid: false,
      // loading: false,
      // required: value => !!value || '必須です',
      // message: '送信',
    }
  },
  methods: {
    send() {
      this.loading = true
      this.$refs.form.reset()
      this.message = '送信成功！！'
    },
    async submit() {
      const params = new FormData()
      //以下、ダミーフォームの各フォーム要素のnameと合わせる
      params.append('form-name', 'contact')
      params.append('name', this.name)
      params.append('email', this.email)
      params.append('company', this.company)
      params.append('message', this.message)
      params.append('bot-field', this.botfield)

      const response = await this.$axios.$post(window.location.origin, params)
      //実際はresponseを使って画面側にフィードバックさせるが、ここでは仮にconsoleに出力
      console.log(response)
    },
  },
}
</script>
