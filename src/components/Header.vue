<template>
  <h1 id="name">Claudio Castorina</h1>
  <div id="desc">
    <p>
      Hello there! I am Claudio, and I'm a freelancer based in Milan, Italy. When
      I'm not designing and developing websites, I am probably working at some
      other data-related projects.
      <a href="#terminal" @click="curiosity">Here</a> you can learn more about me!
      From September 2021 I will be starting my studies in Data Science and Artificial Intelligence at Maastricht University.
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
  padding-top: 8vh;
  width: 100%;
  font-family: "Playfair Display", serif;
  color: #313026;
}

#desc {
  display: flex;
  letter-spacing: 0.3pt;
  font-size: 1.5rem;
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
