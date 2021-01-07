<template>
  <div class="terminal" v-if="isCurious" id="terminal">
    <ul>
      <div><li class="blue">> Claudio.contactInfo</li></div>
      <div class="item">
        <span
          >[<a class="nostyle" href="https://github.com/Casto1387">"GitHub"</a>,
          <a class="nostyle" href="mailto:claudioeugenio.castorina@gmail.com"
            >"mail"</a
          >,
          <a class="nostyle" href="https://www.linkedin.com/in/castori/"
            >"LinkedIn"</a
          >]</span
        >
      </div>
      <li v-for="items in aboutMe" :key="items">
        <div class="blue">
          <li>> Claudio.{{ items.type }}</li>
        </div>
        <div class="item">
          <span>{{ items.cont }}</span>
        </div>
      </li>
      <div><li class="blue">> Claudio.webProjectsInfo</li></div>
      <div class="item">
        "<a class="nostyle" href="#projects" @click="project">click me to learn more</a>"
      </div>
    </ul>
    <ul></ul>
    <p @click="exit">{{ terminalLastRow }}</p>
  </div>
</template>

<script>
export default {
  props: ["aboutMe", "isCurious", "terminalLastRow"],
  methods: {
    exit() {
      this.$emit("uncurious");
    },
    project() {
      this.$emit("project")
    }
  },

};
</script>

<style>
a.nostyle:link {
  text-decoration: inherit;
  color: rgb(68, 139, 184);
  cursor: pointer;
}
a.nostyle:hover {
  color: #b86363 !important;
  transition: 0.6s all;
}

a.nostyle:visited {
  text-decoration: inherit;
  color: rgb(68, 139, 184);
}

.blue {
  color: #5fabe2;
}

.item {
  color: #e6e1a8;
  padding-bottom: 2vh;
  padding-top: 4px;
  margin-left: 1.1rem;
}
.terminal li {
  list-style: none;
}
#terminal > ul {
  margin-left: -2rem;
}
.terminal,
.terminal:before,
.terminal:after,
.terminal p:after {
  position: absolute;
}

.terminal {
  font-family: "Roboto Mono", monospace;
  height: 100vh;
  width: 80vw;
  margin: 0 auto;
  margin-top: 5vh;
  padding: 25px 5px 5px;
  border-radius: 10px;
  background: linear-gradient(
    #f6f9fd,
    #f6f9fd 20px,
    #000000 20px,
    #f6f9fd 21px,
    #1a202c 21px
  );
  box-shadow: 0 0 0 1px rgba(0, 0, 0, 0.5);
  transition: all 0.5s ease;
}

.terminal:before {
  content: " ";
  width: 10px;
  height: 10px;
  margin: -20px 0 0 5px;
  border-radius: 5px;
  background: #fc625d;
  box-shadow: 0 0 0 1px #de413e, 15px 0 #fec041, 15px 0 0 1px #dda035,
    30px 0 #35cc4b, 30px 0 0 1px #28aa36;
}

.terminal p {
  color: #fff;
  font-size: 1rem;
  margin-left: 0.5rem;
  cursor: pointer;
}

.terminal p:hover {
  color: rgb(182, 182, 182);
  transition: 1s all;
}

.terminal p:after {
  animation: blink 1s linear 1s infinite;
  content: " ";
  width: 4px;
  height: 1.3rem;
  margin-left: 5px;
}

@-webkit-keyframes blink {
  0% {
    background: rgb(255, 255, 255, 0);
  }
  50% {
    background: rgb(255, 255, 255, 0);
  }
  51% {
    background: #ffffff;
  }
  100% {
    background: #ffffff;
  }
}

@keyframes blink {
  0% {
    background: rgb(255, 255, 255, 0);
  }
  50% {
    background: rgb(255, 255, 255, 0);
  }
  51% {
    background: #ffffff;
  }
  100% {
    background: #ffffff;
  }
}

@media (max-width: 330px) {
  .terminal {
    margin-left: -1rem;
    font-size: 0.8rem;
  }
  .terminal p {
    font-size: 0.8rem;
  }
}
</style>
