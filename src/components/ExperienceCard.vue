<template>
    <div class="container">
        <div class="line-container">


            <div class="experience-card left-card" v-for="(exp, index) in experience.slice(0, 2)" :key="index">
                <h3>{{ exp.title }}</h3>
                <p>{{ exp.date }}</p>
                <p>{{ exp.company_name }}</p>
                <ul>
                    <li v-for="(point, i) in exp.points" :key="i">{{ point }}</li>
                </ul>
            <div class="circle top-circle"></div>
            <div class="circle middle-circle"></div>
            <div class="circle bottom-circle"></div>
            <div class="circle new-circle"></div>

            <div class="vertical-line"></div>
            </div>

            <div class="experience-card right-card" v-for="(exp, index) in experience.slice(2)" :key="index">
                <h3>{{ exp.title }}</h3>
                <p>{{ exp.date }}</p>
                <p>{{ exp.company_name }}</p>
                <ul>
                    <li v-for="(point, i) in exp.points" :key="i">{{ point }}</li>
                </ul>
            </div>
        </div>
    </div>
</template>

<script>
export default {
    name: 'ExperienCe',
    data() {
        return {
            experience: [
        { 
          title: "Back-end Developer", 
          date: "Oct 2023 - Nov 2023", 
          company_name: "Project Tracker", 
          points: [
            "Developing and maintaining web applications back-end using Flask and mySQL and other related technologies.",
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
            "Developing and maintaining web applications using React.js, mySQL and flask.",
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
    },
};
</script>

<style scoped>
.container {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 100vh;
    position: relative;
}

.line-container {
    position: relative;
    display: flex;
    flex-direction: column;
    align-items: center;
}

.vertical-line {
    width: 2px;
    height: 1000px;
    background-color: white;
    position: relative;
    z-index: 1;
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
    margin-top: 300px;
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
}

.bottom-circle {
    bottom: 0;
    background-image: url('/home/user/vueport/vueport/src/assets/company/starbucks.png');
    background-size: cover;
    background-position: center;
}

.new-circle {
    bottom: 100px; 
    left: 50%;
    transform: translateX(-50%); /* Center horizontally */
    background-image: url('/home/user/vueport/vueport/src/assets/company/starbucks.png'); 
    background-size: cover;
    background-position: center;
}

.left-card,
.right-card {
    width: 45%; 
    padding: 20px;
    background-color: #f0f0f0;
    border-radius: 8px;
    margin-bottom: 20px;
}

.left-card {
    align-self: flex-start;
    margin-right: 20px; 
}

.right-card {
    align-self: flex-end;
    margin-left: 20px; 
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
</style>
