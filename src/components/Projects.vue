<template>
  <div
    v-if="isProject"
    id="projects"
  >
    <div
      class="project-card"
      v-for="project in projects"
      :key="project"
    >
      <img
        class="project-image"
        :src="getImgUrl(project.img)"
      />
      <div class="content">
        <h3>{{ project.title }}</h3>

        <p>
          {{ project.desc }}
        </p>

        <div class="source">
          <div class="left-button">
            <a
              :class="{ disabled: project.isDisabled }"
              :href="project.link"
              :target="project.target"
              class="project-link"
            >Try it out!</a>
          </div>
          <div class="button">
            <a
              :class="{ disabled: project.isDisabled }"
              :href="project.git"
              :target="project.target"
              class="project-link"
            ><svg
                aria-hidden="true"
                data-prefix="fab"
                data-icon="github"
                class="svg-inline--fa fa-github fa-w-16 "
                role="img"
                xmlns="http://www.w3.org/2000/svg"
                viewBox="0 0 496 512"
              >
                <path
                  fill="currentColor"
                  d="M165.9 397.4c0 2-2.3 3.6-5.2 3.6-3.3.3-5.6-1.3-5.6-3.6 0-2 2.3-3.6 5.2-3.6 3-.3 5.6 1.3 5.6 3.6zm-31.1-4.5c-.7 2 1.3 4.3 4.3 4.9 2.6 1 5.6 0 6.2-2s-1.3-4.3-4.3-5.2c-2.6-.7-5.5.3-6.2 2.3zm44.2-1.7c-2.9.7-4.9 2.6-4.6 4.9.3 2 2.9 3.3 5.9 2.6 2.9-.7 4.9-2.6 4.6-4.6-.3-1.9-3-3.2-5.9-2.9zM244.8 8C106.1 8 0 113.3 0 252c0 110.9 69.8 205.8 169.5 239.2 12.8 2.3 17.3-5.6 17.3-12.1 0-6.2-.3-40.4-.3-61.4 0 0-70 15-84.7-29.8 0 0-11.4-29.1-27.8-36.6 0 0-22.9-15.7 1.6-15.4 0 0 24.9 2 38.6 25.8 21.9 38.6 58.6 27.5 72.9 20.9 2.3-16 8.8-27.1 16-33.7-55.9-6.2-112.3-14.3-112.3-110.5 0-27.5 7.6-41.3 23.6-58.9-2.6-6.5-11.1-33.3 2.6-67.9 20.9-6.5 69 27 69 27 20-5.6 41.5-8.5 62.8-8.5s42.8 2.9 62.8 8.5c0 0 48.1-33.6 69-27 13.7 34.7 5.2 61.4 2.6 67.9 16 17.7 25.8 31.5 25.8 58.9 0 96.5-58.9 104.2-114.8 110.5 9.2 7.9 17 22.9 17 46.4 0 33.7-.3 75.4-.3 83.6 0 6.5 4.6 14.4 17.3 12.1C428.2 457.8 496 362.9 496 252 496 113.3 383.5 8 244.8 8zM97.2 352.9c-1.3 1-1 3.3.7 5.2 1.6 1.6 3.9 2.3 5.2 1 1.3-1 1-3.3-.7-5.2-1.6-1.6-3.9-2.3-5.2-1zm-10.8-8.1c-.7 1.3.3 2.9 2.3 3.9 1.6 1 3.6.7 4.3-.7.7-1.3-.3-2.9-2.3-3.9-2-.6-3.6-.3-4.3.7zm32.4 35.6c-1.6 1.3-1 4.3 1.3 6.2 2.3 2.3 5.2 2.6 6.5 1 1.3-1.3.7-4.3-1.3-6.2-2.2-2.3-5.2-2.6-6.5-1zm-11.4-14.7c-1.6 1-1.6 3.6 0 5.9 1.6 2.3 4.3 3.3 5.6 2.3 1.6-1.3 1.6-3.9 0-6.2-1.4-2.3-4-3.3-5.6-2z"
                ></path>
              </svg>
              View on GitHub</a>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ["isProject", "projects"],
  methods: {
    getImgUrl(pic) {
      return require("../assets/" + pic);
    },
  },
};
</script>

<style>
#projects {
  padding-top: 5vh;
}
.disabled {
  cursor: not-allowed;
  background: gray !important;
}

.content {
  width: 70%;
  margin-left: auto;
  margin-bottom: 5vh;
}

.project-card {
  position: relative;
  width: 100%;
  margin: 0 auto;
  height: 60%;
  background: #fff;
  -webkit-box-shadow: 0px 2px 14px 3px rgba(0, 0, 0, 0.75);
  -moz-box-shadow: 0px 2px 14px 3px rgba(0, 0, 0, 0.75);
  box-shadow: 0px 2px 14px 3px rgba(0, 0, 0, 0.75);
  border-radius: 2px;
  font-family: "Playfair Display", serif;
}

.project-card h3 {
  font-size: 2rem;
  padding: 6vh 0 0 7vh;
  color: #313026;
  letter-spacing: 1.3pt;
}

.project-card p {
  font-size: 1.1rem;
  padding: 0 7vh 0 7vh;
  margin-top: -0.3vh;
  color: #313026;
  font-family: "Roboto Mono", monospace;
}

.live {
  margin-top: 6vh;
  width: 100%;
}

.left-button {
  margin-left: 7vh;
  text-align: left;
  float: left;
}

.source {
  padding-bottom: 5vh;
  margin-top: 6vh;
  text-align: right;
  width: 100%;
}

.button {
  margin-right: 7vh;
}

.source a {
  text-decoration: none;
}

svg:not(:root).svg-inline--fa {
  overflow: visible;
}

.svg-inline--fa {
  display: inline-block;
  font-size: inherit;
  height: 1em;
  overflow: visible;
  vertical-align: -0.125em;
}

.svg-inline--fa.fa-w-16 {
  width: 1em;
}

.project-link {
  display: inline-block;
  border-radius: 4px;
  letter-spacing: 0.3pt;
  font-size: 1rem;
  font-family: "Montserrat", sans-serif;
  padding: 12px;
  box-sizing: border-box;
  background: #b86363;
  color: #fff;
  transition: all 0.15s ease;
  -webkit-box-shadow: 0px 0px 6px 1px rgba(0, 0, 0, 0.5);
  -moz-box-shadow: 0px 0px 6px 1px rgba(0, 0, 0, 0.5);
  box-shadow: 0px 0px 6px 1px rgba(0, 0, 0, 0.5);
}

.project-link:hover {
  background: #bb4a4a;
  transform: translateY(-5px);
}

.project-image img {
  padding: 0;
  border: 0;
  font-size: 100%;
  font: inherit;
  vertical-align: baseline;
}

.project-image {
  width: 30%;
  height: 100%;
  position: absolute !important;
  top: 0;
  left: 0;
  filter: blur(5px);
}

@media (max-width: 1090px) {
  .project-image {
    display: none;
  }
  .content {
    width: 100%;
    margin-left: 0;
  }
}

@media (max-width: 540px) {
  .content h3 {
    margin: 0 auto;
    padding: 40px 20px;
    text-align: center;
    font-size: 1.5rem;
  }
  .content p {
    padding: 20px;
    text-align: center;
    font-size: 1rem;
  }
  .button {
    margin: 0;
    text-align: center;
  }
  .left-button {
    float: none;
    text-align: center;
    margin: 0;
    margin-bottom: 1.5rem;
  }
}
</style>
