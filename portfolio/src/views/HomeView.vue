<template>
  <div id="projects">
    <div class="projects_propile"></div>
    <h2 class="projects_title">안녕하세요 신입 웹 개발자 이시빈입니다.</h2>
    <strong class="projects_text"
      >'느린 것을 두려워 말고, 멈추는 것을 두려워하라'</strong
    >
  </div>
  <div id="about">
    about
    <img src="../assets/tree.jpg" alt="첫번째 프로젝트" class="about-img" />
  </div>
  <div id="tech">tech</div>
  <div id="awards">awards</div>
  <div id="blog">blog</div>
</template>

<script>
/* eslint-disable */
export default {
  name: "app",
  data() {
    return {};
  },
  methods: {},
};
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
.about-img {
  position: absolute;
  right: 30px;
  width: auto;
  height: 500px;
  border-radius: 10px;
}
/* tech */
#tech {
  padding: 10px;
  width: auto;
  height: 500px;
  background-color: bisque;
}
/* awards */
#awards {
  padding: 20px;
  width: auto;
  height: 500px;
  background-color: #1b1b1b;
}
/* blog */
#blog {
  padding: 10px;
  width: auto;
  height: 500px;
  background-color: bisque;
}
</style>
