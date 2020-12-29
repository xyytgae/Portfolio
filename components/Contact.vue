<template>
  <v-card color="#e5f6ff" flat>
    <v-card-text class="pb-0 text-center">Contact</v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold"
      ><span class="menu">お問い合わせ</span></v-card-text
    >

    <form name="contact" method="POST" data-netlify="true">
      <input type="hidden" name="form-name" value="contact" />
      <p>
        <label>Your Name: <input type="text" name="name"/></label>
      </p>
      <p>
        <label>Your Email: <input type="email" name="email"/></label>
      </p>
      <p>
        <label
          >Your Role:
          <select name="role[]" multiple>
            <option value="leader">Leader</option>
            <option value="follower">Follower</option>
          </select></label
        >
      </p>
      <p>
        <label>Message: <textarea name="message"></textarea></label>
      </p>
      <p>
        <button type="submit">Send</button>
      </p>
    </form>

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
      inputItems: [
        {
          name: '名前',
        },
        {
          name: 'Email',
        },
        {
          name: '件名',
        },
      ],
      form: {
        name: '',
        email: '',
        title: '',
        contents: '',
      },
      valid: false,
      loading: false,
      required: value => !!value || '必須です',
      message: '送信',
    }
  },
  methods: {
    send() {
      this.loading = true
      this.$refs.form.reset()
      this.message = '送信成功！！'
    },
  },
}
</script>
