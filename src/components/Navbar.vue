<template>
  <div class="container-nav">
    <nav class="navbar">
      <a
        href="#terminal"
        @click="curious"
      >About</a>
      <a
        href="#projects"
        @click="project"
      >Projects</a>
    </nav>
  </div>
</template>

<script>
export default {
  methods: {
    curious() {
      this.$emit("curious");
    },
    project() {
      this.$emit("project");
    },
  },
};
</script>

<style>
.container-nav {
  display: flex;
  margin: 0 auto;
  justify-content: flex-end;
}

@media (max-width: 767px) {
  .container-nav {
    width: 70%;
    justify-content: center;
  }

  .container-nav .navbar {
    font-size: 1rem;
  }
}

.container-nav .navbar {
  display: flex;
  width: 20rem;
  justify-content: space-around;
  font-family: "Playfair Display", serif;
  margin-top: 4vh;
  font-size: 1.6rem;
}

.container-nav .navbar a {
  position: relative;
  color: #313026;
  text-decoration: none;
  transition: 0.6s all;
  margin: 0 10px;
}

.container-nav a:after {
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  margin: 0;
  opacity: 0;
  margin: auto;
  width: 0%;
  color: transparent;
  height: 1px;
  text-align: left;
  content: "";
}

.container-nav a:hover:after {
  width: 100%;
  z-index: -14;
  animation: fill 0.4s forwards;
  -webkit-animation: fill 0.4s forwards;
  -moz-animation: fill 0.4s forwards;
  opacity: 1;
}

.container-nav a:hover {
  color: #fff;
  z-index: 1;
}

@keyframes fill {
  0% {
    width: 0%;
    height: 1px;
  }
  50% {
    width: 100%;
    height: 1px;
  }
  100% {
    width: 100%;
    height: 100%;
    background: #b86363;
  }
}

@-webkit-keyframes fill {
  0% {
    width: 0%;
    height: 1px;
  }
  50% {
    width: 100%;
    height: 1px;
  }
  100% {
    width: 100%;
    height: 100%;
    background: #b86363;
  }
}
</style>
