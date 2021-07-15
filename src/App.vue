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
        { type: "currentLocation", cont: '"Maastricht, NL"' },
        { type: "interests", cont: '["design", "gaming", "data", "fitness"]' },
        {
          type: "technologies",
          cont: '["Python", "Java", "HTML", "CSS", "Javascript", "Vue.js", "Node.js"]',
        },
        { type: "occupation", cont: '"Student"' },
        {
          type: "footerCredits",
          cont: '"Made by Claudio Castorina | Copyright 2021"',
        },
        { type: "favouriteColour", cont: '"#b86363"'},
        {
          type: "languages",
          cont: '["English", "Dutch", "German", "Italian"]',
        },
      ],
      projects: [
        {
          title: "Claudio Castorina's Portfolio",
          desc:
            "That's right, this is the page you're looking at! At the moment I think it's the website that most reflects my style, it was developed with Vue.js 3 to ensure the most personalized experience possible.",
          img: "portfolio.png",
          git: "https://github.com/CaastOS/portfolio",
          link: "#",
          target: "_blank",
        },
        {
          title: "Spotifpy",
          desc:
            'Spotifpy is a web application created in Python and based on Flask and Socket.io. The live version of the website shown below constantly shows what I\'m listening to, see readme for more information.',
          img: "spotifpy.jpg",
          git: "https://github.com/CaastOS/spotifpy",
          link: "https://spotifpy.herokuapp.com",
          target: "_blank",
        },
        {
          title: "MusicHint",
          desc:
            'MusicHint is a side-project I made entirely for fun. What\'s its purpose? It gives you music recommendation! For this project I used Vue.js, JQuery and TasteDive API.',
          img: "musichint.jpg",
          git: "https://github.com/CaastOS/musichint",
          link: "https://musichint.claudiocastorina.com",
          target: "_blank",
        },
        {
          title: "Firewall Gaming",
          desc:
            "Firewall Gaming was one of the most famous eSports associations in Italy around the 2015s. The site was based on Laravel, and my job was to develop the front-end side. The website is not on GitHub, but I'm available to show it to anyone interested.",
          img: "firewallgaming.jpg",
          git: "#",
          link: "#",
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

#terminal > ul:nth-child(1) > li:nth-child(8) > div.item > span:hover {
  color: #b86363;
  transition: 0.3s all;
  cursor: text;
}

</style>
