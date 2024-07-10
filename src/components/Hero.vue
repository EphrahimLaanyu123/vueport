<template>
  <div class="hero">
    <div class="hero__left">
      <div class="hero__circle"></div>
      <div class="hero__circle_line"></div>
    </div>
    <div class="hero__content">
      <h1 class="hero__title">Hi, I'm <span class="highlight">Ephrahim</span></h1>
      <p class="hero__description">
        I am a programmer specialized in the development of <br>
        website applications and user interfaces.
      </p>
    </div>
  </div>
</template>

<script>

export default {
  name: 'HeRo' 
}

</script>

<style scoped>
.hero {
  display: flex;
  justify-content: center;
  height: 100vh;
  text-align: center;
}

.hero__left {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-right: 20px;
}

.hero__circle {
  width: 20px;
  height: 20px; 
  border-radius: 50%; 
  background-color: #915EFF; 
  margin-bottom: 0px;
  margin-top: 0px;
}

.hero__circle_line {
  width: 5px; 
  height: 350px;
  background-color: #915EFF; 
  margin-top: 0px;
  background: linear-gradient(to bottom, rgba(145, 94, 255, 1) 0%, rgba(145, 94, 255, 0) 100%); 

}

.hero__content {
  text-align: left; 
}

.hero__title {
  font-size: 75px;
  line-height: 98px;
  font-weight: 900;
  color: white;
  margin-top: 20px;
}

.hero__description {
  font-size: 30px;
  line-height: 40px;
  font-weight: 500;
  color: #dfd9ff;
  margin-top: 10px;
}

.highlight {
  color: #915EFF;
}
</style>


