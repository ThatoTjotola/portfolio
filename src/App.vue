<template>
  <div id="app">
    <section class="hero">
      <div class="hero-content">
        <img src="/portfolio/mypic.jpg" alt="Jimmy picture" class="profile-picture" />
        <div class="text-content">
          <h1>Welcome to Jimmy Tjotola's Portfolio</h1>
          <p>showcasing some work</p>
          <a href="https://www.linkedin.com/in/jimmy-tjotola-91766126a/" class="btn">View Portfolio</a>
        </div>
      </div>
    </section>

    <section id="portfolio" class="portfolio">
      <h2>Projects</h2>
      <button class="btn" @click="toggleProjects">
        {{ showProjects ? "Hide Projects" : "Show Projects" }}
      </button>
      <div v-if="showProjects">
        <div class="project-card" v-for="project in projects" :key="project.id">
          <img :src="project.image" alt="Project Title" style="width: 300px;" v-if="project.image" />
          <iframe v-if="project.video" :src="project.video" frameborder="0" allowfullscreen></iframe>
          <h3>{{ project.title }}</h3>
          <p>{{ project.description }}</p>
          <a :href="project.link" class="btn">View Project</a>
        </div>
      </div>
    </section>

    <footer>
      <p>&copy; 2024 Jimmy Tjotola. All rights reserved.</p>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      showProjects: true,
      projects: [
        {
          id: 1,
          title: "OpenCV C# Project",
          description: "A facial recognition application using OpenCV.",
          image: "/portfolio/project-image.jpeg",
          link: "https://github.com/ThatoTjotola/FacialRecognitionWindowsFormsAppVersionZERO",
        },
        {
          id: 2,
          title: "BirdView Kotlin Project",
          description: "A bird-tracking app powered by multiple APIs.",
          video: "https://www.youtube.com/embed/HKp_yzcWNVc",
          link: "https://github.com/ThatoTjotola/BirdtrackingKotlinApp",
        },
        {
          id: 3,
          title: "Trivia Game Project",
          description: "A trivia-based game using Kotlin and TriviaDB API.",
          image: "/portfolio//trivia.png",
          link: "https://github.com/ThatoTjotola/TriviaQuestionAppOpenTriviaDatabase",
        },
      ],
    };
  },
  methods: {
    toggleProjects() {
      this.showProjects = !this.showProjects;
    },
  },
};
</script>

<style>
body {
  font-family: 'Arial', sans-serif;
  margin: 0;
  padding: 0;
}

.hero {
  background: #f4f4f4;
  padding: 80px 0;
  text-align: center;
}

.hero-content {
  max-width: 800px;
  margin: 0 auto;
  display: flex;
  align-items: center;
  text-align: left;
}

.profile-picture {
  width: 100px;
  height: 100px;
  border-radius: 50%;
  margin-right: 20px;
}

.text-content {
  flex: 1;
}

.btn {
  display: inline-block;
  background-color: #965858;
  color: white;
  padding: 10px 20px;
  text-decoration: none;
  border-radius: 5px;
  margin-top: 20px;
  cursor: pointer;
}

.portfolio {
  padding: 60px 0;
  text-align: center;
  background-color: #254f7e;
  color: white;
}

.project-card {
  max-width: 600px;
  margin: 0 auto;
}

footer {
  background-color: #333;
  color: white;
  text-align: center;
  padding: 10px 0;
}
</style>
