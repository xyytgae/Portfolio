<template>
  <v-card color="#e5f6ff" flat>
    <v-card-text class="pb-0 text-center">Contact</v-card-text>
    <v-card-text class="py-0 text-center headline font-weight-bold"
      ><span class="menu">お問い合わせ</span></v-card-text
    >
    <!-- 
    <form
      name="contact"
      netlify-honeypot="bot-field"
      data-netlify="true"
      method="post"
    >
      <input type="hidden" name="form-name" value="contact" />
      <p class="hidden" style="display: none;">
        <label>Don’t fill this out: <input name="bot-field"/></label>
      </p>
      <p>
        <label>Email: <input type="text" name="name"/></label>
      </p>
      <p>
        <label>Message: <textarea name="message"></textarea></label>
      </p>
      <p>
        <button type="”submit”">Send</button>
      </p>
    </form> -->

    <v-form ref="form" v-model="valid">
      <form
        name="contact"
        netlify-honeypot="bot-field"
        data-netlify="true"
        method="post"
      >
        <input type="hidden" name="form-name" value="contact" />
        <v-col cols="12" md="3">
          <v-text-field
            name="name"
            outlined
            shaped
            :rules="[required]"
            color="orange"
            v-model="form.name"
            label="名前"
          ></v-text-field>
        </v-col>
        <v-col cols="12" md="3">
          <v-text-field
            name="email"
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
            name="title"
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
            name="message"
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
            type="”submit”"
            color="orange"
            :disabled="!valid"
            :dark="valid"
            x-large
            >送信する</v-btn
          >
        </v-col>
      </form>
    </v-form>
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
      valid: true,

      required: value => !!value || '必須です',
      message: '送信',
    }
  },
}
</script>
