<template>
  <h1 id="name">Claudio Castorina</h1>
  <h2 id="role">Machine Learning Intern @<a
      href="https://iconpro.com/en/"
      class="nostyle"
      target="_blank"
      id="job"
    > IconPro GmbH</a></h2>
  <div id="desc">
    <p>
      I used to develop web applications, now I make machines learn. Learn <a
        href="#terminal"
        class="nostyle"
        @click="curiosity"
      >more</a> about me!
    </p>
  </div>
</template>

<script>
export default {
  emits: ["curious"],
  methods: {
    curiosity() {
      this.$emit("curious");
    },
  },
};
</script>

<style>
#name {
  display: flex;
  letter-spacing: 4.5pt;
  font-size: 3.3em;
  width: 100%;
  font-family: "Playfair Display", serif;
  color: #313026;
  margin-bottom: 0;
}

#role {
  display: flex;
  letter-spacing: -0.3pt;
  padding-left: 0.2vw;
  font-size: 1.2rem;
  width: 100%;
  font-family: "Roboto Mono", serif;
  color: #313026;
  margin-top: 0.5vh;
  margin-bottom: 0.7vh;
}

/* on mobile don't show #role */
@media (max-width: 767px) {
  #role {
    display: none;
  }
}
#job {
  margin-left: 0.8vw;
}
#desc {
  display: flex;
  letter-spacing: -0.3pt;
  font-size: 1.4rem;
  width: 100%;
  font-family: "Roboto Mono", serif;
  color: #313026;
}
#desc a {
  color: rgb(68, 139, 184);
  cursor: pointer;
  transition: 0.6s all;
  text-decoration: none;
}

#desc a:hover {
  color: rgb(158, 15, 15);
  transition: 1s all;
}

@media (max-width: 767px) {
  #name {
    font-size: 3rem;
    text-align: center;
    justify-content: center;
  }
  #desc {
    font-size: 1.3rem;
    text-align: center;
    justify-content: center;
  }
}

@media (max-width: 340px) {
  #name {
    font-size: 2.4rem;
    text-align: center;
    justify-content: center;
  }
  #desc {
    font-size: 1rem;
    text-align: center;
    justify-content: center;
  }
}
</style>
