<template>
  <div class="wrapper">
    <parallax class="section page-header header-filter" :style="headerStyle">
      <div class="container">
        <div class="md-layout">
          <div class="md-layout-item md-size-50 md-small-size-70 md-xsmall-size-100">
            <h1 class="title">My Passions & Personality.</h1>
            <h4>Hi, I'm Vivian. Currently taking full-stack web development bootcamp, aiming to work as a professional web developer locally or globally!</h4>
            <br />
            <md-button
              href="https://www.cakeresume.com/s--1xGDbMhNbFwD1-7BQU2Nlw--/vivian-lo"
              class="md-success md-lg"
              target="_blank"
            >
              <i class="fas fa-play"></i> Resume
            </md-button>
          </div>
        </div>
      </div>
    </parallax>
    <div class="main main-raised">
      <div class="section text-center">
        <div class="container">
          <h2 class="title">A few fun facts about myself.</h2>
          <div class="team">
            <div class="md-layout">
              <div class="md-layout-item md-medium-size-50 md-small-size-100">
                <div class="team-player">
                  <md-card class="md-card-plain">
                    <div class="md-layout-item md-size-50 mx-auto">
                      <img
                        :src="img"
                        alt="Thumbnail Image"
                        class="img-raised rounded-circle img-fluid"
                      />
                    </div>
                    <h4 class="card-title">Hi, I am Vivian</h4>

                    <md-card-content>
                      <p
                        v-for="item in intro.me"
                        :key="item"
                        class="card-description brief-word-me text-left"
                      >{{item}}</p>
                    </md-card-content>
                  </md-card>
                </div>
              </div>
              <div class="md-layout-item md-medium-size-50 md-small-size-100">
                <div class="team-player">
                  <md-card class="md-card-plain">
                    <div class="md-layout-item md-size-50 mx-auto">
                      <img
                        :src="teamImg1"
                        alt="Thumbnail Image"
                        class="img-raised rounded-circle img-fluid"
                      />
                    </div>
                    <h4 class="card-title">I am a banker</h4>

                    <md-card-content>
                      <p
                        v-for="item in intro.banker"
                        :key="item"
                        class="card-description brief-word text-left"
                      >{{item}}</p>
                    </md-card-content>
                  </md-card>
                </div>
              </div>
              <div class="md-layout-item md-medium-size-50 md-small-size-100">
                <div class="team-player">
                  <md-card class="md-card-plain">
                    <div class="md-layout-item md-size-50 mx-auto">
                      <img
                        :src="teamImg2"
                        alt="Thumbnail Image"
                        class="img-raised rounded-circle img-fluid"
                      />
                    </div>
                    <h4 class="card-title">I am also a web developer</h4>

                    <md-card-content>
                      <p
                        v-for="item in intro.engineer"
                        :key="item"
                        class="card-description brief-word text-left"
                      >{{item}}</p>
                    </md-card-content>
                  </md-card>
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="section timeline">
        <div class="container">
          <div class="title text-center">
            <h2 class="title">Here’s What 7 Months Long Online Bootcamp Taught Me</h2>
            <h3>Coding makes me realise the potential in me</h3>
          </div>
          <div class="md-layout">
            <div class="md-layout-item md-size-100 md-small-size-100 mx-auto timeline-tabs">
              <tabs
                :tab-name="['2019/6-7', '2019/8-9', '2019/10-12','Final Project']"
                :tab-icon="['web', 'schedule', 'dashboard', 'school']"
                plain
                nav-pills-icons
                color-button="info"
              >
                <!-- here you can add your content for tab-content -->
                <template slot="tab-pane-1">
                  <h4>{{tabPane1.intro}}</h4>
                  <ProjectCard :projects="tabPane1.items" />
                </template>
                <template slot="tab-pane-2">
                  <h4>{{tabPane2.intro}}</h4>
                  <ProjectCard :projects="tabPane2.items" />
                </template>
                <template slot="tab-pane-3">
                  <h4>{{tabPane3.intro}}</h4>
                  <ProjectCard :projects="tabPane3.items" />
                </template>
                <template slot="tab-pane-4">
                  <h4
                    class="title text-center"
                  >The WAP-D is a men's clothing website for you. It includes casual menswear and business suit.</h4>
                  <h5 class="text-center">
                    <a
                      href="https://newman0934.github.io/wapd-frontend/#/index"
                      target="_blank"
                    >Explore Our Website</a>
                    <br />or view code on
                    <a
                      href="https://github.com/newman0934/wapd-frontend"
                      target="_blank"
                    >
                      <i class="fab fa-github"></i>forntend /
                    </a>
                    <a href="https://github.com/newman0934/wapd-backend" target="_blank">
                      <i class="fab fa-github"></i>backend
                    </a>
                  </h5>
                  <div class="md-layout">
                    <div class="md-layout-item md-size-77 mx-auto md-small-size-100">
                      <md-card>
                        <carousel
                          :per-page="1"
                          loop
                          :speed="700"
                          autoplay
                          :autoplay-timeout="5000"
                          :mouse-drag="false"
                          navigationEnabled
                          navigationNextLabel="<i class='material-icons'>keyboard_arrow_right</i>"
                          navigationPrevLabel="<i class='material-icons'>keyboard_arrow_left</i>"
                        >
                          <slide v-for="slide in slideshow" :key="slide">
                            <!-- <div class="carousel-caption">
                              <h4>
                                <md-icon>location_on</md-icon>Yellowstone National Park, United States
                              </h4>
                            </div>-->
                            <img :src="slide.image" alt="carousel1" />
                          </slide>
                        </carousel>
                      </md-card>
                    </div>
                  </div>
                </template>
              </tabs>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Tabs } from "@/components";
import ProjectCard from "./components/ProjectCard";
export default {
  bodyClass: "landing-page",
  components: {
    Tabs,
    ProjectCard
  },
  props: {
    header: {
      type: String,
      default: "https://i.imgur.com/SP58KpC.jpg"
    },
    img: {
      type: String,
      default: "https://i.imgur.com/gkjfKVl.jpg"
    },
    teamImg1: {
      type: String,
      default: "https://i.imgur.com/Yr1TlMR.png"
    },
    teamImg2: {
      type: String,
      default: "https://i.imgur.com/HAnVE31.png"
    }
  },
  data() {
    return {
      intro: {
        me: [
          "Big Dreams",
          "Responsible",
          "Action Oriented",
          "Versatile",
          "Enthusiastic"
        ],
        banker: [
          "Co-operative and Professional",
          "Alert and Awareness",
          "Reliability",
          "Effective Communication"
        ],
        engineer: [
          "Clear Communication Skills",
          "Ready for the Unexpected",
          "Effectively Managing Risks",
          "Analytical Ability",
          "Team Player",
          "Inquisitive",
          "Open Minded",
          "Non Stop Learning"
        ]
      },
      tabPane1: {
        slot: "tab-pane-1",
        intro:
          "打好 JavaScript 的基礎，了解 JavaScript 在網頁上的延伸應用例如 DOM 操作、AJAX。有能力組合 HTML、CSS 和 JavaScript 做出網路元件，透過實作，一邊學習相關的實務技術如響應式網頁、版本控制、自動化測試等等",
        items: [
          {
            id: 101,
            title: "Personal Website",
            image: "https://i.imgur.com/EYKCto4.png",
            link: "https://codepen.io/YunYuLo/full/orZjzv",
            github: "",
            description: "A static personal website.",
            highlight: ["HTML", "CSS", "RWD"]
          },
          {
            id: 102,
            title: "Guess Number Game",
            image: "https://i.imgur.com/ptBpc0n.png",
            link: "https://repl.it/@YunYuLo/A6-Guess-number-game",
            github: "",
            description: "Guessing the Magician's secret number by algorithm.",
            highlight: ["JS"]
          },
          {
            id: 103,
            title: "Score Board",
            image: "https://i.imgur.com/hDBhGkh.png",
            link: "https://codepen.io/YunYuLo/full/wLpQER",
            github: "",
            description: "A simple basketball scoreboard built by HTML and JS.",
            highlight: ["HTML", "JS", "DOM"]
          },
          {
            id: 103,
            title: "Todo List",
            image: "https://i.imgur.com/Z9MCoUb.png",
            link: "https://codepen.io/YunYuLo/full/vqeMKq",
            github: "",
            description:
              "A simple web application to record tasks and you can easily manage your tasks: add, delete, move to done area.",
            highlight: ["HTML", "CSS", "JS", "DOM"]
          },
          {
            id: 104,
            title: "Costumize Name Card",
            image: "https://i.imgur.com/JExidzG.png",
            link: "https://codepen.io/YunYuLo/full/XLZoWd",
            github: "",
            description:
              "A simple web application to generate name card for you with dark or light theme.",
            highlight: ["HTML", "CSS", "JS", "DOM"]
          },
          {
            id: 105,
            title: "Lottery",
            image: "https://i.imgur.com/fqAvO4l.png",
            link: "https://repl.it/@YunYuLo/lottery-final-task",
            github: "",
            description:
              "A simple lottery algorithm to randomly draw winner with given players.",
            highlight: ["JS"]
          },
          {
            id: 106,
            title: "Adele lyrics",
            image: "https://i.imgur.com/HT7ea4w.png",
            link: "https://codepen.io/YunYuLo/full/BgGNaZ",
            github: "",
            description: "A simple web application for Adele's song lyrics.",
            highlight: ["Axios", "HTML", "Bootstrap", "JS"]
          },
          {
            id: 107,
            title: "Social Page",
            image: "https://i.imgur.com/GCyHfhZ.png",
            link: "https://codepen.io/YunYuLo/full/ZgGROr",
            github: "",
            description:
              "A simple web application for you to learn more about your friends and connect with them. Listing friends' profile from profile API, displaying more detail and managing your favorite list.",
            highlight: ["Axios", "HTML", "Bootstrap", "JS"]
          },
          {
            id: 108,
            title: "Movie List",
            image: "https://i.imgur.com/EyGFzjH.png",
            link: "https://yunyulo.github.io/MovieList-genres/",
            github: "https://github.com/YunYuLo/MovieList-genres",
            description:
              "A simple web application for movie fanatic. Listing movies from movie api and you can search movie by title or genres.",
            highlight: ["Axios", "HTML", "Bootstrap", "JS"]
          },
          {
            id: 109,
            title: "RGB to Hex Converter",
            image: "https://i.imgur.com/uRb5zQr.png",
            link: "https://yunyulo.github.io/RGBtoHexConverter/",
            github: "https://github.com/YunYuLo/RGBtoHexConverter",
            description: "A simple RGB to Hex converter web application.",
            highlight: ["HTML", "CSS", "JS"]
          },
          {
            id: 110,
            title: "Integer to Roman",
            image: "https://i.imgur.com/ptBpc0n.png",
            link: "https://repl.it/@YunYuLo/ACXue-Qi-Er-Qi-Mo-Kao-toRoman",
            github: "",
            description:
              "An interger to roman algorithm with test function to monitor outcome.",
            highlight: ["JS"]
          }
        ]
      },
      tabPane2: {
        slot: "tab-pane-2",
        intro:
          "學會使用 JavaScript + Node.js 打造一個兼具前、後端與資料庫的網路應用程式。學習設計並操作「關聯式」與 NoSQL 資料庫。建立如搜尋、 認證系統、密碼雜湊等簡單功能，並活用 Git/GitHub、終端機/CLI 與 VS Code 來開發與管理專案。同時深入了解 JavaScript 裡 Asynchronous 的特性與 Callback 概念，以及 Promise 與 Async/Await 的應用",
        items: [
          {
            id: 201,
            title: "Password Generator",
            image: "https://i.imgur.com/TXmNiVy.png",
            link: "",
            github: "https://github.com/YunYuLo/password_generator",
            description:
              "A simple web application built to generate password as your selected rules.",
            highlight: ["Nodejs", "Express", "handlebars"]
          },
          {
            id: 202,
            title: "Rubbish Words Generator",
            image: "https://i.imgur.com/4EFEKHx.png",
            link: "https://talkrubbish.herokuapp.com",
            github: "https://github.com/YunYuLo/talk_rubbish_generator",
            description:
              "A fun web application built to generate trash talk based on selected profession.",
            highlight: ["Nodejs", "Express", "handlebars"]
          },
          {
            id: 203,
            title: "Restaurant List",
            image:
              "https://raw.githubusercontent.com/YunYuLo/restaurant_list/master/public/img/main.png",
            link: "",
            github: "https://github.com/YunYuLo/restaurant_list",
            description:
              "A web application built for you to readily manage your restaurant lists with an account: Create, view, edit, delete, filter, sort, and search restaurant.",
            highlight: ["Express", "MongoDB", "Handlebars"]
          },
          {
            id: 204,
            title: "Expense Tracker",
            image:
              "https://raw.githubusercontent.com/YunYuLo/expense-tracker/master/public/img/main.png",
            link: "https://vivi-expense-tracker.herokuapp.com",
            github: "https://github.com/YunYuLo/expense-tracker",
            description:
              "A practical web application built for you to readily record, view, and manage your expense with an account: Create, view, edit, delete, filter expenses.",
            highlight: ["Express", "MongoDB", "Handlebars"]
          },
          {
            id: 205,
            title: "DAILIST",
            image:
              "https://raw.githubusercontent.com/YunYuLo/todo-sequelize/master/public/img/login.png",
            link: "",
            github: "https://github.com/YunYuLo/todo-sequelize",
            description:
              "A practical web application built for you to readily record, view, and manage your tasks with an account: Create, view, edit and delete.",
            highlight: ["Express", "NODEJS", "MySQL"]
          },
          {
            id: 206,
            title: "Short URL",
            image: " https://i.imgur.com/0HFUXkK.png",
            link: "https://vivi-url-shortener.herokuapp.com",
            github: "https://github.com/YunYuLo/url_shortener",
            description:
              "A simple web application built for you to readily get a shortened URL to use.",
            highlight: ["Express", "MongoDB", "Handlebars"]
          }
        ]
      },
      tabPane3: {
        slot: "tab-pane-3",
        intro:
          "活用基礎工具，從功能出發，設計功能背後的跨資料表關聯、自訂路由與前端 helper，並且在小組協作的情況下，活用 Git/GitHub 來解決程式碼的合併衝突、與隊友共同完成專案",
        items: [
          {
            id: 301,
            title: "Restaurant Forum",
            image: "https://i.imgur.com/DRgjTJP.png",
            link: "https://obscure-springs-01735.herokuapp.com/signin",
            github: "https://github.com/YunYuLo/restaurant_forum",
            description:
              "A restaurant forum web application built for you to readily record, view, and manage your restaurant with an account",
            highlight: ["Nodejs", "Express", "mySQL"]
          },
          {
            id: 302,
            title: "Simple Twitter",
            image: "https://i.imgur.com/GUad6XN.png",
            link: "https://ac-simple-twitter-express-vce.herokuapp.com/signin",
            github:
              "https://github.com/newman0934/simple-twitter-express-starter/tree/feature/vivian",
            description:
              "A simple twitter project built with Node.js, Express, and MySQL.",
            highlight: ["Nodejs", "Express", "mySQL"]
          },
          {
            id: 303,
            title: "Calendar",
            image: "https://i.imgur.com/nZEcgqZ.png",
            link: "https://yunyulo.github.io/vue-calendar/",
            github: "https://github.com/YunYuLo/vue-calendar",
            description:
              "Hook up a Firebase Firestore to a custom Vue.js application using the Vuetify calendar component.",
            highlight: ["vue", "vuetify", "firebase"]
          }
        ]
      },
      slideshow: [
        { image: "https://i.imgur.com/Ey6GBQe.jpg" },
        { image: "https://i.imgur.com/PMZF1IZ.jpg" },
        { image: "https://i.imgur.com/rGqV5GF.png" },
        { image: "https://i.imgur.com/6179Yq9.png" },
        { image: "https://i.imgur.com/hKV0WYn.png" },
        { image: "https://i.imgur.com/PUjhs7P.png" }
      ]
    };
  },
  computed: {
    headerStyle() {
      return {
        backgroundImage: `url(${this.header})`
      };
    }
  }
};
</script>

<style lang="scss" scoped>
.brief-word-me {
  font-size: 16px;
  margin: 0 6rem 0;
}
.brief-word {
  font-size: 16px;
  margin: 0 4rem 0;
}
.brief-word::first-letter,
.brief-word-me::first-letter {
  font-weight: bold;
  color: black;
}
.timeline {
  padding: 0 0;
}
.timeline-tabs::v-deep {
  .md-card-tabs .md-list {
    justify-content: center;
  }
}
.md-card-actions.text-center {
  display: flex;
  justify-content: center !important;
}
.contact-form {
  margin-top: 30px;
}

.md-has-textarea + .md-layout {
  margin-top: 15px;
}
</style>
