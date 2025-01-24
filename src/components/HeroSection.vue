<template>
  <section class="relative w-full" id="home" data-aos="zoom-in-up">
    <div class="absolute top-0 inset-x-0 h-64 flex items-start">
      <div
        class="h-24 w-2/3 bg-gradient-to-br from-[#570cac] blur-2xl invisible opacity-40"
      ></div>
      <div
        class="h-20 w-3/5 bg-gradient-to-r from-[#670ccf] opacity-40 blur-2xl py-24"
      ></div>
    </div>
    <div
      class="w-full px-8 sm:px-8 md:px-12 lg:py-48 py-32 lg:px-48 max-w-screen-lg lg:max-w-screen-xl mx-auto relative"
    >
      <div
        class="grid lg:grid-cols-2 gap-10 xl:gap-14 relative lg:max-w-none max-w-2xl md:max-w-3xl mx-auto"
      >
        <div class="lg:py-7">
          <div class="text-center lg:text-left">
            <h1
              class="pt-4 text-white font-bold text-4xl md:text-5xl lg:text-6xl sm:text-5xl"
            >
              Hi, I'm
              <span
                class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-pink-500"
              >
                Rikza Nazilatur
              </span>
            </h1>
            <div class="py-2">
              <h1
                class="typewrite text-xl font-semibold text-transparent bg-clip-text bg-gradient-to-r from-slate-100 to-yellow-500 md:text-2xl fadein-up"
                ref="typewriter"
              >
                <span class="wrap"> {{ txt }}</span>
              </h1>
            </div>
            <p class="text-white pr-4 fade-in-from-left blur-none">
              Welcome to My personal website. <span class="wave">👋🏼</span>
            </p>
            <br />
          </div>
          <div
            class="flex items-center gap-3 pt-0 flex-col sm:flex-col sm:w-max sm:mx-auto lg:mx-0"
          >
            <button
              class="border border-primary px-6 md:px-9 py-3 rounded-full relative group w-full sm:w-max flex justify-center"
            >
              <div
                class="hover:scale-105 transition-all ease-in-out flex justify-center items-center relative"
              >
                <div class="svg-container">
                  <svg
                    class="download-icon"
                    width="18"
                    height="24"
                    viewBox="2 2 21 20"
                    fill="none"
                    xmlns="http://www.w3.org/2000/svg"
                  >
                    <path
                      class="download-arrow"
                      d="M3 16.5v2.25A2.25 2.25 0 0 0 5.25 21h13.5A2.25 2.25 0 0 0 21 18.75V16.5M16.5 12 12 16.5m0 0L7.5 12m4.5 4.5V3"
                      stroke="#f59e0b"
                      stroke-width="2"
                      stroke-linecap="round"
                      stroke-linejoin="round"
                    />
                  </svg>
                  <div class="download-loader text-white hidden"></div>
                </div>
                <a
                  href="@/assets/resume.pdf"
                  download="resume.pdf"
                  class="pl-2 text-primary"
                >
                  Download Resume</a
                >
              </div>
            </button>
          </div>
        </div>
        <div class="lg:h-full md:flex">
          <div
            class="flex w-full h-96 min-h-[22rem] lg:min-h-[none] lg:w-full lg:h-full items-center relative"
          >
            <div
              class="absolute z-0 top-1/2 -translate-y-1/3 w-5/6 right-0 h-[calc(80%+20px)] bg-gradient-to-tr opacity-25 from-[#570cac] to-primary blur-2xl"
            ></div>
            <div
              class="absolute h-full z-10 p-2 -translate-y-1/2 top-1/2 lg:right-10 md:right-40 sm:right-16 rounded-full shadow-lg shadow-primary border border-primary"
            >
              <img
                src="@/assets/pict8.jpeg"
                alt="Hero pict"
                width="500"
                height="auto"
                loading="lazy"
                class="w-full h-full rounded-full object-cover contrast-100 saturate-100 hue-rotate-15"
              />
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>
<script>
export default {
  data() {
    return {
      toRotate: [
        "Web Developer",
        "FrontEnd Engineer",
        "Informatics Student",
        "Tech Enthusiast",
      ],
      period: 2000,
      txt: "",
      loopNum: 0,
      isDeleting: false,
    };
  },
  mounted() {
    this.$nextTick(() => {
      this.tick();
    });
  },
  methods: {
    tick() {
      let typewriter = this.$refs.typewriter;

      if (!typewriter) {
        return;
      }

      let i = this.loopNum % this.toRotate.length;
      let fullTxt = this.toRotate[i];

      this.txt = this.isDeleting
        ? fullTxt.substring(0, this.txt.length - 1)
        : fullTxt.substring(0, this.txt.length + 1);
      typewriter.innerHTML = `<span class="wrap">${this.txt}</span>`;

      let that = this;
      let delta = 200 - Math.random() * 100;

      if (this.isDeleting) {
        delta /= 2;
      }

      if (!this.isDeleting && this.txt === fullTxt) {
        delta = this.period;
        this.isDeleting = true;
      } else if (this.isDeleting && this.txt === "") {
        this.isDeleting = false;
        this.loopNum++;
        delta = 500;
      }

      setTimeout(() => {
        that.tick();
      }, delta);
    },
  },
};
</script>

<style>
body {
  overflow-y: scroll;
  overflow-x: hidden;
}

.typewrite > .wrap {
  border-right: 0.08em solid #fff;
}

.wave {
  animation-name: wave-animation;
  animation-duration: 2.5s;
  animation-iteration-count: infinite;
  transform-origin: 70% 70%;
  display: inline-block;
}

@keyframes wave-animation {
  0% {
    transform: rotate(0deg);
  }

  10% {
    transform: rotate(14deg);
  }

  20% {
    transform: rotate(-8deg);
  }

  30% {
    transform: rotate(14deg);
  }

  40% {
    transform: rotate(-4deg);
  }

  50% {
    transform: rotate(10deg);
  }

  60% {
    transform: rotate(0deg);
  }

  to {
    transform: rotate(0deg);
  }
}

.pict {
  box-shadow: 0px 0px 73px -9px rgba(255, 219, 112, 0.44);
  -webkit-box-shadow: 0px 0px 73px -9px rgba(255, 219, 112, 0.44);
  -moz-box-shadow: 0px 0px 73px -9px rgba(255, 219, 112, 0.44);
}

.fadein-up {
  opacity: 0;
  animation-name: fadeInUp;
  animation-duration: 0.5s;
  animation-fill-mode: forwards;
  animation-delay: 500ms;
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translate3d(0, 100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

.fade-in-from-left {
  opacity: 0;
  animation: fadeInLeft 0.5s ease-out forwards;
  animation-delay: 500ms;
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(-100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadein-right {
  opacity: 0;
  animation: fadeInRight 0.5s ease-out forwards;
  animation-delay: 500ms;
}

@keyframes fadeInRight {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }
  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadein-bot {
  opacity: 0;
  animation: fadeInBot 0.5s forwards;
}

@keyframes fadeInBot {
  from {
    opacity: 0;
    transform: translate3d(0, -100%, 0);
  }

  to {
    opacity: 1;
    transform: translate3d(0, 0, 0);
  }
}

.fadein-1 {
  animation-delay: 200ms;
}
.fadein-2 {
  animation-delay: 400ms;
}
.fadein-3 {
  animation-delay: 600ms;
}
.fade-500 {
  animation-delay: 500ms;
}
</style>
