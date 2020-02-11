<template>
  <div>
    <div>
      <div class="features text-center">
        <div class="md-layout md-gutter md-alignment-center">
          <div
            v-for="item in items"
            :key="item.id"
            class="md-layout-item md-large-size-33 md-small-size-50 md-xsmall-size-100"
          >
            <a :href="item.link?  item.link: item.github" target="_blank">
              <md-card class="md-primary" md-theme="purple-card" md-with-hover>
                <md-card-media-cover>
                  <md-card-media md-ratio="16:9" class="hovereffect">
                    <img :src="item.image" />
                    <div class="overlay">
                      <h2>{{item.description}}</h2>
                      <!-- <a class="info">link here</a> -->
                    </div>
                  </md-card-media>
                  <md-card-actions>
                    <div class="md-layout-item">
                      <badge v-for="(tag,index) in item.highlight" :key="index" type="info">{{tag}}</badge>
                    </div>
                  </md-card-actions>
                </md-card-media-cover>
                <md-card-content>
                  <h5 class="md-title">{{item.title}}</h5>
                  <!-- <div class="md-subhead">{{item.description}}</div> -->
                </md-card-content>
                <md-card-footer>
                  <md-button
                    v-if="item.github"
                    :href="item.github"
                    target="_blank"
                    class="md-rose md-round md-sm"
                  >
                    <i class="fab fa-github"></i>github
                  </md-button>
                  <md-button
                    v-if="item.link"
                    :href="item.link"
                    target="_blank"
                    class="md-success md-round md-sm"
                  >
                    <i class="fas fa-eye"></i>demo
                  </md-button>
                </md-card-footer>
              </md-card>
            </a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { Badge } from "@/components";
export default {
  components: {
    Badge
  },
  props: {
    projects: {
      type: Array,
      required: true
    }
  },
  data() {
    return {
      items: this.projects
    };
  }
};
</script>

<style lang="css">
.hovereffect {
  width: 100%;
  height: 100%;
  /* float: left; */
  overflow: hidden;
  position: relative;
  text-align: center;
  cursor: default;
}

.hovereffect .overlay {
  width: 100%;
  height: 100%;
  position: absolute;
  overflow: hidden;
  top: 0;
  left: 0;
  opacity: 0;
  background-color: rgba(0, 0, 0, 0.5);
  -webkit-transition: all 0.4s ease-in-out;
  transition: all 0.4s ease-in-out;
}

.hovereffect img {
  display: block;
  position: relative;
  -webkit-transition: all 0.4s linear;
  transition: all 0.4s linear;
}

.hovereffect h2 {
  /* text-transform: uppercase; */
  color: #fff;
  text-align: center;
  position: relative;
  font-size: 17px;
  background: rgba(0, 0, 0, 0.6);
  -webkit-transform: translatey(-100px);
  -ms-transform: translatey(-100px);
  transform: translatey(-100px);
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  padding: 10px;
}

.hovereffect a.info {
  text-decoration: none;
  display: inline-block;
  text-transform: uppercase;
  color: #fff;
  border: 1px solid #fff;
  background-color: transparent;
  opacity: 0;
  filter: alpha(opacity=0);
  -webkit-transition: all 0.2s ease-in-out;
  transition: all 0.2s ease-in-out;
  margin: 50px 0 0;
  padding: 7px 14px;
}

.hovereffect a.info:hover {
  box-shadow: 0 0 5px #fff;
}

/* .hovereffect:hover img {
  -ms-transform: scale(1.2);
  -webkit-transform: scale(1.2);
  transform: scale(1.2);
} */

.hovereffect:hover .overlay {
  opacity: 1;
  filter: alpha(opacity=100);
}

.hovereffect:hover h2,
.hovereffect:hover a.info {
  opacity: 1;
  filter: alpha(opacity=100);
  -ms-transform: translatey(0);
  -webkit-transform: translatey(0);
  transform: translatey(0);
}

.hovereffect:hover a.info {
  -webkit-transition-delay: 0.2s;
  transition-delay: 0.2s;
}
</style>