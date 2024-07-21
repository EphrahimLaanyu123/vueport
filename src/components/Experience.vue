<template>
  <div class="main-div">
    <h1 class="exp-h1">WHAT I HAVE DONE SO FAR</h1>
    <h2 class="exp-h2">PROJECT EXPERIENCE</h2>
    <div class="container">
      <div class="left-cards">
        <div class="experience-card left-card-1">
          <h3>{{ experience[0].title }}</h3>
          <p>{{ experience[0].date }}</p>
          <p>{{ experience[0].company_name }}</p>
          <ul>
            <li v-for="(point, i) in experience[0].points" :key="i">{{ point }}</li>
          </ul>
        </div>

        <div class="experience-card left-card-2">
          <h3>{{ experience[2].title }}</h3>
          <p>{{ experience[2].date }}</p>
          <p>{{ experience[2].company_name }}</p>
          <ul>
            <li v-for="(point, i) in experience[2].points" :key="i">{{ point }}</li>
          </ul>
        </div>
      </div>

      <div class="line-container">
        <div class="circle top-circle"></div>
        <div class="circle middle-circle"></div>
        <div class="circle bottom-circle"></div>
        <div class="circle new-circle"></div>

        <div class="vertical-line"></div>
      </div>

      <div class="right-cards">
        <div class="experience-card right-card-1">
          <h3>{{ experience[1].title }}</h3>
          <p>{{ experience[1].date }}</p>
          <p>{{ experience[1].company_name }}</p>
          <ul>
            <li v-for="(point, i) in experience[1].points" :key="i">{{ point }}</li>
          </ul>
        </div>

        <div class="experience-card right-card-2">
          <h3>{{ experience[3].title }}</h3>
          <p>{{ experience[3].date }}</p>
          <p>{{ experience[3].company_name }}</p>
          <ul>
            <li v-for="(point, i) in experience[3].points" :key="i">{{ point }}</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'ExperIence',
  data() {
    return {
      experience: [
        { 
          title: "Back-end Developer", 
          date: "Oct 2023 - Nov 2023", 
          company_name: "Project Tracker", 
          points: [
            "Developing and maintaining web applications back-end using Flask and MySQL and other related technologies.",
            "Collaborating with cross-functional teams including designers, product managers, and other developers to create high-quality products."
          ]
        },
        { 
          title: "React JS Developer", 
          date: "Oct 2023 - Nov 2023", 
          company_name: "Project Tracker", 
          points: [
            "Developing and maintaining web applications using React.js and other related technologies.",
            "Collaborating with cross-functional teams including designers, product managers, and other developers to create high-quality products.",
            "Implementing responsive design and ensuring cross-browser compatibility.",
            "Participating in code reviews and providing constructive feedback to other developers."
          ]
        },
        { 
          title: "Full stack developer", 
          date: "Sept 2022 - Oct 2023", 
          company_name: "ChatWave", 
          points: [
            "Developing and maintaining web applications using React.js, MySQL and Flask.",
            "Collaborating with cross-functional teams including designers, product managers, and other developers to create high-quality chat app.",
            "This was built from scratch by my team and me to enhance communication within our classroom."
          ]
        },
        { 
          title: "Full stack Developer", 
          date: "Jan 2024 - Present", 
          company_name: "Portfolio", 
          points: [
            "Developing and maintaining web applications using React.js and other related technologies.",
            "This is meant to bring my clients and people who are interested in my services closer to me and get a feel of what I do.",
            "Also shows a wide range of services I can offer.",
            "Having a contact page enables the clients to easily contact me via email."
          ]
        }
      ]
    };
  }
};
</script>

<style scoped>
.main-div {
    
}
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100%;
    gap: 50px;
    margin-top:-750px;
}

.line-container {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
    margin-top: 20px; 
    margin-bottom: 20px; 
    
}

.vertical-line {
    width: 4px;
    height: 1700px;
    background-color: white;
    position: relative;
    z-index: 1;
    margin-top:800px;
}

.circle {
    width: 70px;
    height: 70px;
    background-color: white;
    border-radius: 50%;
    position: absolute;
    z-index: 2;
}

.top-circle {
    top: 0;
    margin-top: 830px;
    background-image: url('/home/user/vueport/vueport/src/assets/company/starbucks.png');
    background-size: cover;
    background-position: center;
}

.middle-circle {
    top: 50%;
    transform: translateY(-50%);
    background-image: url('/home/user/vueport/vueport/src/assets/company/starbucks.png');
    background-size: cover;
    background-position: center;
    margin-top: -80px;
}

.bottom-circle {
    top: 50%;
    transform: translateY(-50%);
    background-image: url('/home/user/vueport/vueport/src/assets/company/starbucks.png');
    background-size: cover;
    background-position: center;
    margin-top: 800px;

}

.new-circle {
    top: 50%;
    transform: translateY(-50%);
    background-image: url('/home/user/vueport/vueport/src/assets/company/starbucks.png');
    background-size: cover;
    background-position: center;
    margin-top: 400px;

}

.left-cards,
.right.cards
{
    display: flex;
    flex-direction: column;
    align-items: center;
    
}
.left-cards {
    gap: 500px;
}

.right-cards {
    gap: 500px;
}

.left-card-1,
.left-card-2,
.right-card-1,
.right-card-2 {
    width: 45%;
    padding: 20px;
    border-radius: 8px;
    margin-bottom: 10px; 
    width: 350px;
    flex-grow: 1;
    justify-content: center;
    align-items: center;
    background:#1d1836;
    color:"#fff";
    
}

.left-card-1 {
    align-self: flex-start;
    margin-right: 0px; 
    margin-top: 300px;       

}

.left-card-2 {
    align-self: flex-start;
    margin-left: 20px;
  

 
}

.right-card-1 {
    margin-right: 20px; 
    height: 400px;
    margin-top: 980px;

}

.right-card-2 {

    margin-left: 20px; 
    margin-top: 500px; 
}

.experience-card h3 {
    font-size: 20px;
    margin-bottom: 8px;
}

.experience-card p {
    font-size: 14px;
    margin-bottom: 4px;
}

.experience-card ul {
    margin-top: 8px;
    padding-left: 20px;
}

.experience-card li {
    font-size: 14px;
    line-height: 1.6;
}

.exp-h1 {
    font-size: 20px; 
    color: white; 
    text-transform: uppercase; 
    letter-spacing: 0.05em;
    text-align: center; 
    margin: 0;
    margin-top: 150px;
}

.exp-h2 {
    font-size: 60px; 
    color: white;
    font-weight: bolder;
    text-transform: uppercase; 
    letter-spacing: 0.05em; 
    text-align: center;
    margin: 0;
    letter-spacing: 0.025em;

}
/* Responsive styles */
@media (max-width: 768px) {
  .container {
    flex-direction: column;
    margin-top: 20px;
  }

  .line-container {
    display: none;
  }

  .left-cards,
  .right-cards {
    gap: 20px;
  }

  .left-card-1,
  .left-card-2,
  .right-card-1,
  .right-card-2 {
    width: 90%;
    margin: 10px auto;
    margin-top: 0; 
  }

  .exp-h1 {
    font-size: 16px;
    margin-top: 20px;
  }

  .exp-h2 {
    font-size: 40px;
  }
}
</style>
