<template>
  <my-header v-model:links="links" @scrollToSection="scrollToSection"></my-header>
  <my-welcome></my-welcome>
  <my-aboutUs></my-aboutUs>
  <my-frameworks :frameworks="frameworks"></my-frameworks>
  <my-miniContact></my-miniContact>
  <my-application :applications="applications"></my-application>
  <my-contactUs></my-ContactUs>
  <my-footer></my-footer>
</template>

<script>

import myAboutUs from '@/components/AboutUs.vue';
import myHeader from '@/components/Header.vue';
import myWelcome from '@/components/Welcome.vue';
import myFrameworks from '@/components/Frameworks.vue';
import myMiniContact from '@/components/MiniContact.vue';
import myApplication from '@/components/Applications.vue';
import myContactUs from '@/components/ContactUs.vue';
import myFooter from '@/components/Footer.vue';
export default {

  components: {
    myAboutUs, myHeader, myWelcome, myFrameworks, myMiniContact, myApplication, myContactUs, myFooter
  },

  data() {
    return {

      positionSections: [],

      frameworksImages: {
        vue: require('@/../public/img/vue.png'),
        react: require('@/../public/img/react.png'),
        angular: require('@/../public/img/angular.png'),
      },

      applicationsImages: {
        first: require('@/../public/img/application-1.png'),
        second: require('@/../public/img/application-2.png'),
        third: require('@/../public/img/application-3.png'),
        fourth: require('@/../public/img/application-4.png'),
        fifth: require('@/../public/img/application-5.png'),
        sixth: require('@/../public/img/application-6.png'),
        seventh: require('@/../public/img/application-7.png'),
        eighth: require('@/../public/img/application-8.png')
      },

      frameworks: [
        {
          id: 1, img: '', name: 'Vue js', text: `Vue.js is an open source JavaScript framework for creating user interfaces.
         It is easily integrated into projects using other JavaScript libraries. It can function as a web framework for
          developing single-page applications in a reactive style.` },
        {
          id: 2, img: '', name: 'React js', text: `React is an open source JavaScript library for developing user interfaces. 
        Instagram Facebook, React is developed and supported by a community of individual developers and corporations.
         React can be used to develop single-page and mobile applications.` },
        {
          id: 3, img: '', name: 'Angular js', text: `AngularJS is an open source JavaScript framework. 
        Designed for the development of single-page applications.
         Its goal is to expand browser applications based on the MVC template, as well as simplify testing and development.` },
      ],
      applications: [
        { id: 1, img: '', name: 'App 1' },
        { id: 2, img: '', name: 'App 2' },
        { id: 3, img: '', name: 'App 3' },
        { id: 4, img: '', name: 'App 4' },
        { id: 5, img: '', name: 'App 5' },
        { id: 6, img: '', name: 'App 6' },
        { id: 7, img: '', name: 'App 7' },
        { id: 8, img: '', name: 'App 8' }
      ]
    }
  },

  methods: {
    sendImages() {
      this.frameworks[0].img = this.frameworksImages.vue;
      this.frameworks[1].img = this.frameworksImages.react;
      this.frameworks[2].img = this.frameworksImages.angular;

      let appImages = Object.values(this.applicationsImages);
      let i = 0;
      for (let application of this.applications) {
        application.img = appImages[i];
        i++;
      }
    },
    scrollToSection(link) {
      let sections = document.querySelectorAll('section');

      for (let section of sections) {
        if (link.name == 'home') {
          document.body.scrollIntoView({
            behavior: 'smooth'
          });
        }
        else if (link.name == section.className) {
          section.scrollIntoView({
            behavior: 'smooth'
          });
        }
      }
    },
    getSectionsCoords() {
      let sections = document.querySelectorAll('section');
      for (let section of sections) {
        let sectionPosition = section.getBoundingClientRect();
        let topPosition = sectionPosition.top + window.pageYOffset - document.querySelector('.header__container').getBoundingClientRect().height;
        this.positionSections.push(topPosition);
      }
      this.showLink(this.positionSections);
    },

    showLink(coords) {
      document.addEventListener('scroll', function (event) {
        let headerLinks = document.querySelector('.nav').querySelectorAll('a');

        if (window.pageYOffset >= coords[0] && window.pageYOffset < coords[1]) {
          for (let i = 0; i < headerLinks.length; i++) {
            if (i == 0) {
              headerLinks[0].style.color = '#71A3FF';
            } else {
              headerLinks[i].style.color = '#3D3D3D';
            }
          }
        } else if (window.pageYOffset >= coords[1] && window.pageYOffset < coords[2]) {
          for (let i = 0; i < headerLinks.length; i++) {
            if (i == 1) {
              headerLinks[1].style.color = '#71A3FF';
            } else {
              headerLinks[i].style.color = '#3D3D3D';
            }
          }
        } else if (window.pageYOffset >= coords[2] && window.pageYOffset < coords[3]) {
          for (let i = 0; i < headerLinks.length; i++) {
            if (i == 2) {
              headerLinks[2].style.color = '#71A3FF';
            } else {
              headerLinks[i].style.color = '#3D3D3D';
            }
          }
        }
        else if (window.pageYOffset >= coords[3] && window.pageYOffset < coords[4]) {
          for (let i = 0; i < headerLinks.length; i++) {
            if (i == 3) {
              headerLinks[3].style.color = '#71A3FF';
            } else {
              headerLinks[i].style.color = '#3D3D3D';
            }
          }
        }
        else if (window.pageYOffset >= coords[4] && window.pageYOffset < coords[5]) {
          for (let i = 0; i < headerLinks.length; i++) {
            if (i == 4) {
              headerLinks[4].style.color = '#71A3FF';
            } else {
              headerLinks[i].style.color = '#3D3D3D';
            }
          }
        }
      }
      )
    }

  },
  mounted() {
    this.sendImages();
    this.getSectionsCoords();
  }
}
</script>

<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Gothic+A1:wght@400;700&family=Roboto:wght@400;500&display=swap');

$dark: #3D3D3D;
$grey: #808080;

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Gothic A1', sans-serif;
  font-weight: 400;
}

body {
  background: #F5F7FA;
}

a,
li {
  text-decoration: none;
  list-style: none;
}

img {
  display: block;
}

.section-name {
  font-weight: 700;
  font-size: 28px;
  line-height: 35px;
  color: $dark;
}

.btns {
  padding-top: 16px;
  display: flex;
  align-items: center;
}
</style>
