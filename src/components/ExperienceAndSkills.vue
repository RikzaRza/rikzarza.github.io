<template>
  <section class="text-white mt-18" id="skills">
    <div class="px-5 py-5 md:px-12 md:py-10 text-left text-amber-50 mx-3">
      <article data-page="about">
        <header class="mt-20">
          <div
            class="text-2xl font-bold text-white fadein-bot title-section flex items-center"
          >
            <div
              class="h-[1px] w-10 bg-amber-200 md:w-20 aos-init aos-animate"
              data-aos="zoom-in-left"
              data-aos-duration="600"
            ></div>
            &nbsp; Skills
          </div>
        </header>
        <div>
          <ul
            class="flex flex-wrap text-md my-7 font-medium text-center text-gray-500 dark:text-gray-400 mb-5"
          >
            <li class="mr-2">
              <button
                class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{
                  'text-amber-200 bg-amber-200 bg-opacity-10': activeTab === 1,
                }"
                @click="activeTab = 1"
              >
                Tech Stack
              </button>
            </li>
            <li class="mr-2">
              <button
                class="inline-block px-4 py-3 rounded-lg hover:text-white"
                :class="{
                  'text-amber-200 bg-amber-200 bg-opacity-10': activeTab === 2,
                }"
                @click="activeTab = 2"
              >
                Tools
              </button>
            </li>
          </ul>
        </div>
        <div v-show="activeTab === 1" data-aos="zoom-in-up">
          <div
            class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12"
          >
            <div v-for="item in tech" :key="item.id">
              <div
                class="item-tech flex cursor-pointer items-center gap-2 rounded border border-amber-200 px-2 py-2 hover:bg-amber-200 hover:bg-opacity-10 md:gap-3 lg:px-3"
              >
                <div
                  class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in"
                >
                  <img
                    alt="HTML"
                    loading="lazy"
                    width="32"
                    height="32"
                    decoding="async"
                    data-nimg="1"
                    class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                    :src="item.imageUrl"
                    style="color: transparent"
                  />
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div
                    class="tech font-medium text-secondary transition-all duration-300 translate-y-0"
                  >
                    {{ item.name }}
                  </div>
                  <div
                    class="status-tech opacity-0 absolute mt-5 text-[10px] text-amber-200 transition-all duration-300 md:text-xs lg:text-sm"
                  >
                    {{ item.status }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div v-show="activeTab === 2" data-aos="zoom-in-up">
          <div
            class="grid grid-cols-2 gap-4 pb-32 md:grid-cols-3 md:gap-8 xl:grid-cols-4 xl:gap-10 2xl:gap-12"
          >
            <div v-for="item in tools" :key="item.id">
              <div
                class="item-tech flex cursor-pointer items-center gap-2 rounded border border-amber-200 px-2 py-2 hover:bg-amber-200 hover:bg-opacity-10 md:gap-3 lg:px-3"
              >
                <div
                  class="flex h-12 w-12 items-center justify-center p-0 lg:h-16 lg:w-16 lg:p-2 zoom-in"
                >
                  <img
                    alt="HTML"
                    loading="lazy"
                    width="32"
                    height="32"
                    decoding="async"
                    data-nimg="1"
                    class="img-tech drop-shadow-xl transition-all duration-300 h-[65%] w-[65%] lg:h-[85%] lg:w-[85%]"
                    :src="item.imageUrl"
                    style="color: transparent"
                  />
                </div>
                <div class="flex items-center text-sm md:text-base lg:text-lg">
                  <div
                    class="tech font-medium text-secondary transition-all duration-300 translate-y-0"
                  >
                    {{ item.name }}
                  </div>
                  <div
                    class="status-tech opacity-0 absolute mt-5 text-[10px] text-amber-200 transition-all duration-300 md:text-xs lg:text-sm"
                  >
                    {{ item.status }}
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </article>
    </div>
  </section>
  <!--<section class="text-white mt-18" id="skills">
        <div class="absolute right-0 top-[110rem] h-full w-full justify-end">
            <span class="flex opacity-20">
                <span class="w-16 h-32 rounded-l-full flex bg-primary blur-2xl"></span>
                <span class="w-16 h-32 rounded-r-full flex bg-[#f88fc2] blur-2xl mt-14"></span>
            </span>
        </div>
        <div class="md:grid md:grid-cols-2 gap-8 items-center py-28 px-4 xl:gap-16 xl:px-16">
            <div class="mt-4 md:mt-0 text-left flex flex-col z-10 h-full w-[80%]">
                <h2 class="text-4xl font-bold text-white text-left mb-4">My
                    <span class="text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">Skills</span>
                </h2>
                <div class="mt-8" v-for="skill in Skills" :key="skill.id">
                    <div class="flex items-end justify-between" data-aos="fade-right">
                        <h4 class="font-semibold uppercase text-white">
                            {{ skill.name }}
                        </h4>
                        <h3 class="text-2xl font-bold text-white">{{ skill.width }}</h3>
                    </div>
                    <div class="mt-2 h-1 w-full bg-[#131d30] rounded-full">
                        <div class="h-1 rounded-full bg-primary" :style="`width :${skill.width}`"></div>
                    </div>
                </div>
            </div>
            <div data-aos="flip-left">
                <h2 class="text-4xl font-bold text-white text-left mb-8 md:text-center md:mt-0 mt-8">My Experience</h2>
                <div class="space-y-8 py-8" data-aos="fade-left">
                    <div v-for="element in Experience" :key="element.id"
                    class="flex items-center rounded-xl p-4 bg-[#111a3e] shadow-lg border border-[#1f1641]">
                    <div class="w-1/4">
                        <img src="https://img.icons8.com/ios-filled/100/ffffff/lawyer.png" alt="lawyer">
                    </div>
                    <div class="w-3/4 pl-5">
                        <h3 class="text-2xl font-semibold uppercase text-transparent bg-clip-text bg-gradient-to-r from-primary to-secondary">
                            {{ element.role }}
                        </h3>
                        <p class="text-white">{{ element.company }}</p>
                        <p class="text-white">{{ element.date }}</p>
                    </div>
                    </div>
                </div>
            </div>
        </div>
    </section>-->
</template>
<script>
export default {
  data() {
    return {
      activeTab: 1,
      tech: [
        {
          id: 1,
          name: "HTML",
          imageUrl: "https://cdn-icons-png.flaticon.com/512/1051/1051277.png",
          status: "Advanced",
        },
        {
          id: 2,
          name: "CSS",
          imageUrl: "https://cdn-icons-png.flaticon.com/512/732/732190.png",
          status: "Advanced",
        },
        {
          id: 3,
          name: "PHP",
          imageUrl:
            "https://cdn.iconscout.com/icon/free/png-256/free-php-2038871-1720084.png",
          status: "Advanced",
        },
        {
          id: 4,
          name: "Javascript",
          imageUrl:
            "https://img.icons8.com/?size=100&id=108784&format=png&color=000000",
          status: "Advance",
        },
        {
          id: 5,
          name: "Laravel",
          imageUrl: "https://cdn.worldvectorlogo.com/logos/laravel-2.svg",
          status: "Advance",
        },
        {
          id: 6,
          name: "Codeigniter",
          imageUrl:
            "https://img.icons8.com/?size=100&id=DtBPN1O4CCnF&format=png&color=000000",
          status: "Intermediate",
        },
        {
          id: 7,
          name: "VueJS",
          imageUrl:
            "https://cdn.iconscout.com/icon/free/png-256/free-vue-282497.png?f=webp",
          status: "Intermediate",
        },
        {
          id: 8,
          name: "AlpineJS",
          imageUrl:
            "https://avatars.githubusercontent.com/u/59030169?s=200&v=4",
          status: "Beginner",
        },
        {
          id: 9,
          name: "NodeJS",
          imageUrl:
            "https://cdn.iconscout.com/icon/free/png-256/free-node-js-1174925.png",
          status: "Beginner",
        },
        {
          id: 10,
          name: "Tailwind",
          imageUrl:
            "https://upload.wikimedia.org/wikipedia/commons/d/d5/Tailwind_CSS_Logo.svg",
          status: "Advance",
        },
        {
          id: 11,
          name: "Bootstrap",
          imageUrl:
            "https://getbootstrap.com/docs/5.2/assets/brand/bootstrap-logo-shadow.png",
          status: "Intermediate",
        },
        {
          id: 12,
          name: "ReactJS",
          imageUrl:
            "https://cdn4.iconfinder.com/data/icons/logos-3/600/React.js_logo-512.png",
          status: "Beginner",
        },
      ],
      tools: [
        {
          id: 1,
          name: "Git",
          imageUrl:
            "https://git-scm.com/images/logos/downloads/Git-Icon-1788C.png",
          status: "Version Control",
        },
        {
          id: 2,
          name: "GitHub",
          imageUrl: "https://cdn-icons-png.flaticon.com/512/25/25231.png",
          status: "Git Hosting",
        },
        {
          id: 3,
          name: "NPM",
          imageUrl:
            "https://cdn.iconscout.com/icon/free/png-256/free-npm-3-1175132.png",
          status: "Package Manager",
        },
        {
          id: 4,
          name: "MySQL",
          imageUrl: "https://cdn-icons-png.flaticon.com/512/5968/5968313.png",
          status: "Database",
        },
      ],
    };
  },
};
</script>
<!--<script setup>
import {ref} from'vue';
const Skills =ref([
    {
        id:1,
        name:'Html & CSS',
        width:'85%',
    },
    {
        id:2,
        name:'Python',
        width:'70%',
    },
    {
        id:3,
        name:'Javascript',
        width:'98%',
    },
    {
        id:4,
        name:'Figma',
        width:'91%',
    },
])

const Experience =ref([
    {
        id:1,
        role:'Software Enginer',
        company:'Microsoft',
        date:'Mar 2023 - September 2024'
    },
    {
        id:2,
        role:'Frontend Developer',
        company:'Microsoft',
        date:'Mar 2023 - September 2024'
    },
])
</script>-->

<style>
.fadein-left {
  opacity: 0;
  animation: fadeInLeft 0.5s ease-out forwards;
}

@keyframes fadeInLeft {
  0% {
    opacity: 0;
    transform: translateX(100%);
  }

  100% {
    opacity: 1;
    transform: translateX(0);
  }
}

.fadeins-1 {
  animation-delay: 500ms;
}

.fadeins-2 {
  animation-delay: 800ms;
}

.img-tech,
.tech {
  transition: transform 0.3s ease;
}

.item-tech:hover .img-tech {
  transform: scale(1.3);
}

.item-tech:hover .tech {
  transform: translateY(-12px);
}

.item-tech:hover .status-tech {
  opacity: 1;
}
</style>
