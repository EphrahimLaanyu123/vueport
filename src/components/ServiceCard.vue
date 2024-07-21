<template>
  <div>
    <h1 class="h1">Introduction</h1>
    <h2 class="h2">Overview.</h2>
    <p class="p">
      "I am an adept software developer proficient in JavaScript, React, Python, MySQL, and Flask. <br>
      With a strong foundation in these technologies, I specialize in crafting efficient, scalable, <br>
      and user-friendly solutions. As a quick learner, I thrive on collaborating closely with clients <br>
      to bring their ideas to fruition and address real-world challenges effectively. Let's collaborate <br>
      to transform your concepts into reality!"
    </p>

    <ul class="service-list">
      <li class="service-card" v-for="service in services" :key="service.title">
        <img :src="service.icon" alt="Service Icon" class="icon" />
        <h3 class="title">{{ service.title }}</h3>
      </li>
    </ul>
  </div>
</template>

<script>
  // Import your icons or placeholders
  import web from '@/assets/web.png';
  import mobile from '@/assets/mobile.png';
  import backend from '@/assets/backend.png';

  export default {
    name: 'ServiceCard',
    data() {
      return {
        services: [
          { title: "Web Developer", icon: web },
          { title: "React Native Developer", icon: mobile },
          { title: "Backend Developer", icon: backend },
          { title: "Flask Developer", icon: web }
        ]
      };
    }
  };
</script>

<style scoped>
.service-list {
  display: flex;
  flex-direction: column;
  align-items: center;
  padding: 0;
  list-style-type: none;
  margin-top: 50px;
}

.service-card {
  width: 90%;
  max-width: 1050px;
  height: 200px;
  margin-bottom: 20px;
  background: linear-gradient(to right, #64b5f6, #f48fb1);
  padding: 10px;
  border-radius: 20px;
  box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.1);
  transition: transform 0.3s ease-in-out;
  text-align: center;
  position: relative;
}

.icon {
  width: 50px;
  height: 50px;
  object-fit: contain;
  position: absolute;
  top: 20px;
  left: 50%;
  transform: translateX(-50%);
}

.title {
  color: #ffffff;
  font-size: 20px;
  font-weight: bold;
  margin-top: 60px;
}

.service-card:hover {
  transform: translateY(-5px);
}

.h1 {
  font-size: 20px;
  color: white;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin: 20px 20px 0;
  text-align: center;
}

.h2 {
  font-size: 40px;
  font-weight: bolder;
  color: white;
  text-transform: uppercase;
  letter-spacing: 0.05em;
  margin: 20px;
  text-align: center;
}

.p {
  font-size: 16px;
  color: #E8E5E4;
  letter-spacing: 0.05em;
  margin: 20px;
  text-align: center;
}

@media (min-width: 768px) {
  .service-list {
    margin-top: 100px;
  }

  .h1 {
    font-size: 20px;
    margin-left: 400px;
  }

  .h2 {
    font-size: 60px;
    margin-left: 400px;
  }

  .p {
    font-size: 18px;
    margin-left: 400px;
  }
}
</style>
