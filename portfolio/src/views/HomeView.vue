<template>
  <div id="projects">
    <div class="projects_propile"></div>
    <h2 class="projects_title">안녕하세요 신입 웹 개발자 이시빈입니다.</h2>
    <strong class="projects_text"
      >'느린 것을 두려워 말고, 멈추는 것을 두려워하라'</strong
    >
  </div>
  <component :is="choice"></component>
  <div id="about">
    일정 관리 앱
    <div class="about_do" @click="page1()"></div>
  </div>
  <div id="tech">
    tech
    <div class="tech_do" @click="page1()"></div>
  </div>
  <div id="awards">
    awards
    <div class="awards_do" @click="page1()"></div>
  </div>
  <div id="blog">
    blog
    <div class="blog_do" @click="page1()"></div>
  </div>
</template>

<script>
/* eslint-disable */
export default {
  name: 'app',
  data() {
    return {}
  },
  methods: {
    page1: function () {
      var link = 'http://localhost:8080/page1'
      window.location.href = link
    },
    page2: function () {
      var link = 'http://localhost:8080/page2'
      window.location.href = link
    },
    page3: function () {
      var link = 'http://localhost:8080/page3'
      window.location.href = link
    },
    page4: function () {
      var link = 'http://localhost:8080/page4'
      window.location.href = link
    }
  }
}
</script>

<style>
body {
  margin: 0;
  padding: 0;
}
/* projects */
#projects {
  padding: 10px;
  width: auto;
  height: 500px;
  background-color: bisque;
}
.projects_propile {
  width: 400px;
  height: 400px;
  background-color: white;
  border-radius: 200px;
  position: absolute;
  left: 80px;
  top: 130px;
}
.projects_title {
  position: absolute;
  top: 150px;
  right: 700px;
}
.projects_text {
  position: absolute;
  top: 230px;
  right: 750px;
}
/* about */
#about {
  padding: 20px;
  width: auto;
  height: 500px;
  background-color: #1b1b1b;
}
.about_do {
  width: 300px;
  height: 450px;
  border-radius: 10px;
  background-color: wheat;
  position: absolute;
  right: 30px;
}
/* tech */
#tech {
  padding: 10px;
  width: auto;
  height: 500px;
  background-color: bisque;
}
.tech_do {
  width: 300px;
  height: 450px;
  border-radius: 10px;
  background-color: #1b1b1b;
  position: absolute;
  left: 30px;
}
/* awards */
#awards {
  padding: 20px;
  width: auto;
  height: 500px;
  background-color: #1b1b1b;
}
.awards_do {
  width: 300px;
  height: 450px;
  border-radius: 10px;
  background-color: wheat;
  position: absolute;
  right: 30px;
}
/* blog */
#blog {
  padding: 10px;
  width: auto;
  height: 500px;
  background-color: bisque;
}
.blog_do {
  width: 300px;
  height: 450px;
  border-radius: 10px;
  background-color: #1b1b1b;
  position: absolute;
  left: 30px;
}
</style>
