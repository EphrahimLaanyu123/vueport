<template>
<div>
  <div class="texts">
    <h1 class="h1">My work</h1>
    <h2 class="h2">Projects</h2>
    <p class="p">
    Following projects showcases my skills and experience through real-world examples of<br>
     my work. Each project is briefly described with links to code repositories and live demos in <br>
     it. It reflects my ability to solve complex problems, work with different technologies, and <br>
     manage projects effectively.
     </p>
  </div>
  <div class="works">
    <div class="works-card" v-for="work in works" :key="work.name">
      <div class="works-header">
        <img :src="work.image" :alt="work.name" class="works-image" />
        <a :href="work.source_code_link" target="_blank" class="source-code-link">
          <img src="@/assets/github.png" class="github-icon" />
        </a>
      </div>
      <h2 class="works-title">{{ work.name }}</h2>
      <p class="works-description">{{ work.description }}</p>
      <ul class="tags">
        <li v-for="tag in work.tags" :key="tag.name" :class="tag.color">#{{ tag.name }}</li>
      </ul>
    </div>
  </div>
</div>

</template>

<script>
export default {
  name: 'WorKs',
  data() {
    return {
      works: [
        {
          name: "Project Tracker",
          description: "Web-based platform that allows programmers to keep track of their projects and different cohorts in order to make it easier for them.",
          tags: [
            { name: "react", color: "blue-text-gradient" },
            { name: "mySQL", color: "green-text-gradient" },
            { name: "tailwind", color: "pink-text-gradient" },
            { name: "flask", color: "pink-text-gradient" }
          ],
          image: require('@/assets/jobit.png'),
          source_code_link: "https://github.com/arnold-aswan/project-tracker-frontend"
        },
        {
          name: "ChatWave",
          description: "Web application that enables users to have a chat. Note: Currently under maintenance",
          tags: [
            { name: "react", color: "blue-text-gradient" },
            { name: "restapi", color: "green-text-gradient" },
            { name: "css", color: "pink-text-gradient" },
            { name: "flask", color: "pink-text-gradient" },
            { name: "socketio", color: "green-text-gradient" }
          ],
          image: require('@/assets/jobit.png'),
          source_code_link: "https://github.com/EphrahimLaanyu123/Chatwave-project"
        },
        {
          name: "Portfolio",
          description: "A comprehensive look on my services and how my clients can easily contact.",
          tags: [
            { name: "Reactjs", color: "blue-text-gradient" },
            { name: "tailwind", color: "green-text-gradient" },
            { name: "three", color: "pink-text-gradient" }
          ],
          image: require('@/assets/tripguide.png'),
          source_code_link: "https://github.com/EphrahimLaanyu123/portfolio"
        }
      ]
    }
  }
}
</script>

<style>
.works {
  display: flex;
  flex-wrap: wrap;
  gap: 20px;
  justify-content: center;
  margin-top: 100px;
}

.works-card {
  width: 300px;
  display: flex;
  flex-direction: column;
  border-radius: 8px;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: hidden;
  transition: transform 0.2s;
}

.works-card:hover {
  transform: translateY(-10px);
}

.works-header {
  position: relative;
}

.works-image {
  border-radius: 8px;
  width: 100%;
  height: 200px;
  object-fit: cover;
}

.source-code-link {
  position: absolute;
  top: 10px;
  right: 10px;
  color: black;
  font-size: 24px;
  text-decoration: none; 
}

.source-code-link img {
  filter: grayscale(100%) invert(0); 
  background-color: black;
  border-radius: 8px;
}

.github-icon {
  width: 24px;
  height: 24px;
}

.works-title {
  font-size: 1.5em;
  margin: 0.5em;
}

.works-description {
  padding: 0 1em 1em;
}

.tags {
  display: flex;
  flex-wrap: wrap;
  list-style: none;
  padding: 0 1em 1em;
  margin: 0;
}

.tags li {
  margin-right: 0.5em;
  font-size: 0.875em;
}

.blue-text-gradient {
  color: #007bff;
}

.green-text-gradient {
  color: #28a745;
}

.pink-text-gradient {
  color: #e83e8c;
}

.texts {
  margin-left: 400px;
}

.h1 {
  font-size: 20px; 
  color: white;
  text-transform: uppercase; 
  letter-spacing: 0.05em; 
  margin: 0; 
  margin-top: 150px;
}

.h2 {
  font-size: 60px; 
  color: white; 
  font-weight: bolder;
  text-transform: uppercase;
  letter-spacing: 0.05em; 
  margin-top: 20px; 
  letter-spacing: 0.025em;
}

.p {
  font-size: 18px;
  color: white; 
  letter-spacing: 0.05em; 
  margin: 0; 
  letter-spacing: 0.025em;
}


@media (max-width: 1024px) {
  .texts {
    margin-left: 0; 
    text-align: center; 
  }
  
  .works {
    margin-top: 50px; 
  }
  
  .works-card {
    width: 250px; 
  }

  .works-header {
    position: relative;
  }

  .source-code-link {
    top: 5px; 
    right: 5px;
  }
  
  .works-title {
    font-size: 1.25em;
  }

  .works-description {
    padding: 0 0.5em 0.5em; 
  }

  .tags li {
    font-size: 0.75em;
  }
}

@media (max-width: 768px) {
  .works-card {
    width: 100%;
    margin: 10px 0; 
  }

  .works-image {
    height: 150px; 
    width: 50%;

  }

  .works-title {
    font-size: 1.1em;
  }

  .works-description {
    padding: 0 0.5em; 
  }

  .tags li {
    font-size: 0.7em; 
  }
  
  .texts {
    margin-left: 0;
    text-align: center; 
    padding: 0 1em; 
  }

  .h1 {
    font-size: 18px; 
    margin-top: 50px; 
  }

  .h2 {
    font-size: 40px; 
  }

  .p {
    font-size: 16px;
  }
}
</style>
