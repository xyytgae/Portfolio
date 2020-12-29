<template>
  <v-row>
    <v-col cols="12" id="profile" class="my-12 active">
      <Profile />
    </v-col>

    <v-col cols="12" id="background" class="my-12 inactive">
      <Background />
    </v-col>

    <v-col cols="12" id="skills" class="my-12 inactive">
      <Skills />
    </v-col>

    <v-col cols="12" id="firstWork" class="my-12 inactive">
      <Work1 />
    </v-col>

    <v-col cols="12" id="secondWork" class="my-12 inactive">
      <Work2 />
    </v-col>

    <v-col cols="12" id="contact" class="my-16 inactive">
      <Contact />
    </v-col>
  </v-row>
</template>

<script>
export default {
  methods: {
    startObserve() {
      const callback = (entries, observer) => {
        entries.forEach(entry => {
          if (entry.isIntersecting) {
            // 初めにopacitty: 0にしていたinactiveクラスを取り除く
            entry.target.classList.remove('inactive')

            // activeクラスを追加することでフェードインさせる
            entry.target.classList.add('active')
          }
        })
      }

      const option = {
        threshold: [0.2, 1.0],
      }

      const observer = new IntersectionObserver(callback, option)

      const targets = document.querySelectorAll('.inactive')
      targets.forEach(target => {
        observer.observe(target)
      })
    },
  },
  mounted() {
    window.onload = () => {
      this.startObserve()
    }
  },
}
</script>

<style lang="scss">
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

.inactive {
  opacity: 0;
}

@keyframes fadeRight {
  0% {
    opacity: 0;
    transform: translateX(300px);
  }

  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.active {
  animation: fadeRight 4s ease 0s 1 normal;
}
</style>
