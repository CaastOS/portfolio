<template>
  <div class="container-main">
    <Navbar @curious="curious" @project="project" />
    <Header @curious="curious" />
    <Terminal
      id="terminal"
      :aboutMe="aboutMe"
      :isCurious="isCurious"
      :terminalLastRow="terminalLastRow"
      @uncurious="uncurious"
      @project="project"
    />
    <Projects :isProject="isProject" :projects="projects" />
  </div>
</template>

<script>
import Navbar from "./components/Navbar.vue";
import Header from "./components/Header.vue";
import Terminal from "./components/Terminal.vue";
import Projects from "./components/Projects.vue";

export default {
  name: "Portfolio",
  components: {
    Navbar,
    Header,
    Terminal,
    Projects,
  },
  data() {
    return {
      isUrl: false,
      aboutMe: [
        { type: "currentLocation", cont: '"Milan, Italy"' },
        { type: "interests", cont: '["Design", "gaming", "data", "fitness"]' },
        {
          type: "technologies",
          cont: '["Python", "Vue.JS", "Flask", "Javascript"]',
        },
        { type: "occupation", cont: '"Student"' },
        {
          type: "footerCredits",
          cont: '"Made by Claudio Castorina | Copyright 2021"',
        },
        { type: "favouriteColour", cont: '"#b86363"' },
        {
          type: "languages",
          cont: '["English", "Dutch", "German", "Italian"]',
        },
      ],
      projects: [
        {
          title: "Claudio Castorina's Portfolio",
          desc:
            "That's right, this is the page you're looking at! At the moment I think it's the website that most reflects my style, it was developed with Vue.js 3 and nothing else! All CSS, HTML and Javascript was developed to ensure the most personalized experience possible.",
          img: "portfolio.png",
          git: "https://github.com/Casto1387/portfolio",
          target: "_blank",
        },
        {
          title: "Camera D'Ascolto",
          desc:
            '"Camera D\'Ascolto" was definitely the most difficult site to develop, as I was specifically required to use Mobirise, a "what you see is what you get" type editor. The hard part was to edit all the blocks to the lowest possible level and to be able to make it all work. The heroic act is on Github, although getting the hang of it is very complicated.',
          img: "cameradascolto.jpg",
          git: "https://github.com/Casto1387/cameradascolto",
          target: "_blank",
        },
		{
          title: "Blackjack Web Application",
          desc:
            "This is a web application made as a hobby a while ago. As the title explains, it's a fully functional though relatively basic blackjack. It is done completely in vanilla javascript.",
          img: "blackjack.jpg",
          git: "https://github.com/Casto1387/blackjack"
        },
        {
          title: "Cimenailfilm",
          desc:
            "Cimenailfilm was the first site I created, and unfortunately I no longer have the source code. The site can be found on the wayback machine, and in any case I wanted to mention it because it was the beginning of everything, for me. It was entirely made in Bootstrap.",
          img: "cimenailfilm.jpeg",
          git: "#",
          isDisabled: true,
        },
        {
          title: "Firewall Gaming",
          desc:
            "Firewall Gaming was one of the most famous eSports associations in Italy around the 2015s. The site was created on Laravel, and my job was to develop the front-end side. The website is not on github for copyright reasons, but I'm available to show it to anyone interested.",
          img: "firewallgaming.jpg",
          git: "#",
          isDisabled: true,
        }
		
      ],
      isCurious: false,
      isProject: false,
      terminalLastRow: "> click me to exit ",
    };
  },
  methods: {
    curious() {
      this.terminalLastRow = "> click me to exit ";
      this.isCurious = true;
      this.isProject = false;
    },
    uncurious() {
      this.terminalLastRow = "> Sorry to see you go :(";
      setTimeout(() => {
        this.isCurious = false;
      }, 1000);
    },
    project() {
      this.isCurious = false;
      this.isProject = true;
    },
  },
};
</script>

<style>
@import url("https://fonts.googleapis.com/css2?family=Merriweather:wght@300&family=Playfair+Display&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300&display=swap");
@import url("https://fonts.googleapis.com/css2?family=Montserrat:wght@400&display=swap");

html {
  background-color: #f6f9fd;
  scroll-behavior: smooth !important;
  height: 100%;
  box-sizing: border-box;
}

.container-main {
  width: 80%;
  margin: 0 auto;
  padding-bottom: 0.6rem;
}
</style>
