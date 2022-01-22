<template>
  <div class="container-main">
    <Navbar
      @curious="curious"
      @project="project"
    />
    <Header @curious="curious" />
    <Terminal
      id="terminal"
      :aboutMe="aboutMe"
      :isCurious="isCurious"
      :terminalLastRow="terminalLastRow"
      @uncurious="uncurious"
      @project="project"
    />
    <Projects
      :isProject="isProject"
      :projects="projects"
    />
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
        { type: "interests", cont: '["Guitar", "Languages", "Bouldering"]' },
        {
          type: "technologies",
          cont: '["Java", "MongoDB", "Express", "Vue.js", "Node.js", "SASS", "PUG"]',
        },
        {
          type: "footerCredits",
          cont: '"Made by Claudio Castorina | Copyright 2021"',
        },
        { type: "favouriteColour", cont: '"#b86363"' },
        {
          type: "languages",
          cont: '["English", "German", "Italian"]',
        },
      ],
      projects: [
        {
          title: "Claudio Castorina's Portfolio",
          desc:
            "That's right, this is the page you're looking at! This is the first real website I developed in Vue.js 3, but it continues to be a work that I proudly display, even after almost a year since its original development. Bringing my attention from React to Vue, I can say that this is the project that has influenced me the most.",
          img: "portfolio.png",
          git: "https://github.com/CaastOS/portfolio",
          link: "#",
          target: "_blank",
        },
        {
          title: "3D Knapsack Solver",
          desc:
            "JavaFX-driven application to visualize different algorithms in the solving of three-dimensional knapsack problems. Different algorithms such as Knuth's Dancing Links and GAs are implemented and discussed in both the README and report.",
          img: "knapsack.png",
          git: "https://github.com/CaastOS/3dknapsacksolver",
          isDisabled: true,
          target: "_blank",
        },
        {
          title: "The Trapped Knight",
          desc:
            "Based on the chess-based problem invented by Neil Sloane, \"The Trapped Knight\" is a vanilla Javascript application that allows you to simulate this problem in real time. It also allows you to bend the rules of the simulation itself, making it much more interesting and interactive. Once the problem has come to an end, an interactive graph will be displayed with all the data needed to understand its path.",
          img: "trappedknight.png",
          git: "https://github.com/CaastOS/trappedknight",
          link: "https://trappedknight.claudiocastorina.com/",
          target: "_blank",
        },
        {
          title: "Spotifpy",
          desc:
            'Spotifpy is a web application created in Python and based on Flask and Socketio. Its purpose is simple, it shows the song you\'re listening to on Spotify in a nice graphical interface, to be displayed on a possible unused second monitor (or at least, that\'s what I do!). The live version shown below constantly shows what I\'m listening to, but I\'ve posted a release on GitHub so that everyone can use this program with their own Spotify profile.',
          img: "spotifpy.jpg",
          git: "https://github.com/CaastOS/spotifpy",
          link: "https://spotifpy.herokuapp.com",
          target: "_blank",
        },
        {
          title: "MidiPlayer",
          desc:
            "MidiPlayer is a DAW (digital audio workstation), i.e. a web application that simulates a musical work environment and allows you to compose music. To set myself a personal challenge, I decided not to use any library to help me, and to build this application solely in plain Javascript. The application is based on Vue.js 3 and uses SASS as CSS extension language.",
          img: "midiplayer.jpg",
          git: "https://github.com/CaastOS/midiplayer",
          link: "https://midiplayer.claudiocastorina.com",
          target: "_blank",
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
