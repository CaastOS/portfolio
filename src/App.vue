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
        { type: "interests", cont: '["Guitar", "Bouldering"]' },
        {
          type: "programmingLanguages",
          cont: '["Python", "Java", "C++", "Javascript"]',
        },
        {
          type: "languages",
          cont: '["English", "Italian"]',
        },
        {
          type: "footerCredits",
          cont: '"Made by Claudio Castorina | Copyright 2023"',
        },
      ],
      projects: [
        {
          title: "Yoda Summarizer",
          desc:
            "NLP academic project that summarizes news using the weird english syntax Yoda speaks in Star Wars. Different stages of the project use different NLP techniques, such as transfomers finetuning (T5, Pegasus, BART), Graph-based Text Summarization (TextRank) and POS Tagging (spaCy). This project was done in a group of four people, more credits and information can be found in the academic report.",
          img: "yoda.jpg",
          git: "https://github.com/CaastOS/3dknapsacksolver",
          isDisabled: true,
          target: "_blank",
        },
        {
          title: "3D Knapsack Solver",
          desc:
            "JavaFX-driven application to visualize different algorithms in the solving of three-dimensional knapsack problems. Different algorithms such as Knuth's Dancing Links and GAs are implemented and discussed in both the README and academic report.",
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
            'Spotifpy is a web application created in Python and based on Flask and Socketio. Its purpose is simple, it shows the song you\'re listening to on Spotify in a nice graphical interface, to be displayed on a possible unused second monitor (or at least, that\'s what I do!). The live version shown below constantly shows what I\'m listening to, but I\'ve posted a release on GitHub so that everyone can use this program with their own Spotify profile. Even though Spotify now has a full-screen version which does literally this, at the time of creation it didn\'t, so I decided to create it myself.',
          img: "spotifpy.jpg",
          git: "https://github.com/CaastOS/spotifpy",
          link: "https://spotifpy.herokuapp.com",
          target: "_blank",
        },
      ],
      isCurious: false,
      isProject: false,
      terminalLastRow: "> exit ",
    };
  },
  methods: {
    curious() {
      this.terminalLastRow = "> exit ";
      this.isCurious = true;
      this.isProject = false;
    },
    uncurious() {
      this.terminalLastRow = "> :(";
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
