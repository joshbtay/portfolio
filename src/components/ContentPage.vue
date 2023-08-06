<template class="Site">
<div class="midline">
<div class="right-content">
<transition mode="out-in" appear>
<div class="middle">
<div class="swapper">
<div class="image-group">
<transition mode="out-in" appear name="down">
<div class="image-ball"></div>
</transition>
<transition mode="out-in" appear name="up">
<img src="../assets/me.png" class="me-image"/>
</transition>
</div>
<div class="bio">
<span class="big-name">JOSH TAYLOR</span>
<span class="job-title">Software Engineer</span>
<div class="contact-info">
<template v-for="link in populatedLinks" :key="link.name">
<transition appear>
<a :href=link.url target="_blank" class="link"><img :src=link.image class="contact-icon"/><span>{{ link.name }}</span><img src="../assets/upright.svg" class="popup"/></a>
</transition>
</template>
</div>
<div style="height:150px"/>
</div>
</div>
<div class="about">
<div class="about-info">
<transition mode="out-in" appear name="up">
<div class="about-left">
<span class="about-blurb">&emsp;&emsp;Hello, I'm Josh Taylor, a software engineer. As an intern at Roblox, I batched DynamoDB writes using Kafka and Flink, saving over $100,000 a month. I also implemented client retries, reducing client-side errors by 90%. During my internship at Lucid Software, I developed ownership transfer features using Angular and Scala, saving 300 hours of work, and improved webpage load time by 93% through optimized TypeScript. Thanks for stopping by!
</span>
</div>
</transition>
<transition appear name="up">
<div class="about-right">
<span style="margin-left: 3px" class="bold">Skills</span>
<div class="about-right-child">
<template v-for="skill in populatedSkills" :key="skill">
<transition appear name="up">
<span>{{ skill }}</span>
</transition>
</template>
</div>
</div>
</transition>
</div>
</div>
<div class="portfolio">
<template v-for="project in populatedProjects" :key=project.caption>
<transition appear name="up">
<a class="image-with-caption" target="_blank" :href=project.url>
<div class="image-container"><img :src="project.image"></div>
<span>{{ project.caption }}</span>
<span class="ital small">{{ project.text }}</span>
</a>
</transition>
</template>
</div>
</div>
</transition>
</div>
</div>
<div class="footer">made by Josh Taylor</div>
</template>

<script>
export default {
  name: 'ContentPage',
  props: {
  },
  mounted () {
   this.loadLinks();
   this.loadPortfolio();
    this.loadSkills();
  },
  data () {
   let context = 'home';
   const timer = ms => new Promise(res => setTimeout(res, ms));
   
   return {
    context,
    timer,
    skills: [
"C",
"C++",
"C#",
"Python",
"Java",
"JavaScript",
"TypeScript",
"Dart",
"HTML",
"CSS",
"Scala",
"SQL",
"Bash",
"Node.js",
"Vue",
"Angular",
"React",
"Flutter",
"AWS",
"Linux",
"Git",
"Firebase",
"PyTorch",
"Agile/Scrum",
"CI/CD",
],
   populatedSkills: [],
   projects: [
   {
    caption: "Competitive Programming Leaderboard",
    url: "https://kattis-leaderboard.web.app",
    image: "leaderboard.png",
    text: "Leaderboard to track BYU students' progress practicing for Competitive Programming"
   },
   {
    caption: "Reversi AI",
    url: "https://github.com/joshbtay/Reversi-AI",
    image: "reversi.gif",
    text: "Alpha-beta algorithm that won the class tournament",
   },
   {
    caption: "Music Generator",
    url: "https://soundcloud.com/joshbtay/sets/transformer-results",
    image: "music.png",
    text: "Deep neural network architecture that generates songs",
   },
   {
    caption: "Family Map",
    url: "https://github.com/joshbtay/family-map",
    image: "family.png",
    text: "Full-stack Android app for users to view their family history on a map",

   },
   {
    caption: "Sour Chat",
    url: "https://github.com/joshbtay/sour-chat",
    image: "sour.png",
    text: "Web app using websockets for users to draw with friends on the same canvas in real-time",

   },
   {
    caption: "ASCII Converter",
    url: "https://github.com/joshbtay/ascii-converter",
    image: "ascii.png",
    text: "Image rendering tool that converts image data to ascii text",

   },
   {
    caption: "Tweeter",
    url: "https://github.com/joshbtay/tweeter",
    image: "tweeter.png",
    text: "Twitter clone built with Java and AWS"
   },
   
   ],
   populatedProjects: [],
   links: [
   {
    name: "linkedin",
    url: "https://linkedin.com/in/joshbtay",
    image: "linkedin.svg"
   },
   {
    name: "github",
    url: "https://github.com/joshbtay",
    image: "github.svg"
   },
   {
    name: "joshbtay@gmail.com",
    url: "mailto: joshbtay@gmail.com",
    image: "contact.svg"
   },
   {
    name: "208-570-5158",
    url: "tel:208-570-5158",
    image: "phone.svg"
   },
   {
    name: "resume",
    url: "Josh_Taylor_resume.pdf",
    image: "download.svg"
   }
   ],
   populatedLinks: [],
   }
  }, 
  methods: {
   async loadSkills() {
    this.populatedSkills=[];
    await this.timer(700);
    for (var i = 0; i < this.skills.length; i++){
     this.populatedSkills.push(this.skills[i]);
     await this.timer(70);
    }
   },
   async loadPortfolio() {
    this.populatedProjects=[];
     await this.timer(500);
    for (var i = 0; i < this.projects.length; i++){
     this.populatedProjects.push(this.projects[i]);
     await this.timer(250);
    }
   },
   async loadLinks() {
    this.populatedLinks = [];
    await this.timer(500);
    for (var i = 0; i < this.links.length; i++){
     this.populatedLinks.push(this.links[i]);
     await this.timer(200);
    }
   }
  },
}
</script>

<style scoped>
.midline {
 display: flex;
 width: 100%;
 background-color: #ffffff;
 flex: 1;
 justify-content: center;
}
.bullet {
 letter-spacing: 1px;
 height: 30px;
 transition: letter-spacing 0.3s;
 cursor: pointer;
 opacity: 0.6;
 user-select: none;
}
.nav{
 text-align: left;
 margin: 15px 30px 15px 45%;
}
.nav-logo{
 max-height: 16px;
 padding-right: 5px;
}
.bullet:hover{
 opacity: .8;
 letter-spacing: 3px;
}

.image-group{
 position: relative;
}

.image-ball{
 width: 100%;
 height: 400px;
 clear: both;
 position: absolute;
 background: rgb(68,87,227);
 background: linear-gradient(0deg, rgba(68,87,227,1) 0%, rgba(147,238,255,1) 100%);
 z-index: 0;
 border-radius: 100%;
}
.small-ball{
 width: 180px;
 height: 180px;
 clear: both;
 position: absolute;
 background: rgb(68,87,227);
 background: linear-gradient(0deg, rgba(68,87,227,1) 0%, rgba(147,238,255,1) 100%);
 z-index: 0;
 right: -130px;
 border-radius: 100%;
}

.me-image{
 border-radius: 100%;
 max-height: 400px;
 max-width: 400px;
 z-index: 1;
 position: relative;
}

.big-name {
 font-size: 48px;
 font-family: 'Poppins', sans-serif;
 font-weight: 900;
}

.job-title {
 font-size: 24px;
 border-top: solid 5px;
 padding-top: 8px;
 font-weight: 400;
}

.under-name {
 color: rgba(0, 0, 0, 0.7);
 margin-top: 40px;
 font-style: italic;
 font-weight: 400;
}

.contact-info {
 margin-top: 40px;
 display: flex;
 justify-content: space-between;
 align-items: flex-start;
 flex-direction: column;
 width: 100%;
 max-height:0;
}

.bold{
 font-weight: 600;
}

.ital{
 font-style:italic;
}

.link {
 color: #000;
 margin-top: 5px;
 opacity: 0.6;
 display: flex;
 text-decoration: none;
 align-items: center;
 transition: all 0.35s ease-out;
 white-space: nowrap;
 font-size: 16px;
}


.contact-icon {
 max-width: 16px;
 margin-right: 8px;
}

.popup {
 opacity: 0;
 max-width: 12px;
 margin: 0 8px;
 transition: all 0.35s ease-out;
}
.link:hover .popup{
 opacity: 0.5;
}
.link:hover {
 opacity: 0.8;
}

.middle{
  text-align: center;

}

.bio {
 display: flex;
 flex-direction: column;
 align-items: flex-start;
 text-align: left;
 margin: 50px;
}

.swapper {
 margin-top: 150px;
 display: flex;
 justify-content: center;
 align-items: center;
 height: 100%;
}

.active {
 opacity: 1;
 letter-spacing: 3px;
}

.right-content{
 width: min(90vw, 1400px);
 margin: auto;
}

.title{
 font-size: 23px;
 font-family: 'Open Sans', sans-serif;
 font-weight: 800;
}

.profile-image{
 max-width: min(80%, 700px);
}

.about {
 display: flex;
 flex-direction: column;
 margin: 5vw;
 align-items: center;
}

.about-info{
 display: flex;
 width: 100%;
}

.about-left{
 width: 65%;
 margin-top: 40px;
 text-align: left;
 display: flex;
 flex-direction: column;
 margin-right: 50px;
}

.about-right{
 width: 35%;
 margin-top: 50px;
 text-align: left;
}

.about-right-child{
 margin-top: 40px;
 display: flex;
 flex-direction: row;
 flex-wrap: wrap;
}

.about-right-child span{
 padding: 4px 8px;
 margin: 5px;
 margin-left: 0;
 border: solid 1px black;
 border-radius: 50px;
 transition: all .25s ease-out;
}

.about-right-child span:hover{
 background-color: black;
 color: white;
}


.about-title{
 display: flex;
 flex-wrap: wrap;
 white-space: pre;
 font-weight:600;
 font-size: 24px;
 padding-bottom: 15px;
 position: relative;
}

.about-blurb{
 margin-top: 32px;
 font-weight: 300;
}

.about-blurb a{
 color: black;
}

.about-title span{
 margin-right: 32px;
}

.download{
 -webkit-filter: invert(100%);
 filter: invert(100%);
 max-height: 16px;
 display: inline-block;
 margin-right: 10px;
}

.download-button{
 font-size: 18px;
 text-decoration: none;
 color: #fff;
 background-color: #000;
 padding: 10px 20px;
 transition: all .35s ease-out;
 align-self: start;
 margin-top: 32px;
 display: flex;
 align-items: center;
 min-width: 100px;
}

.download-button:hover{
 background-color: #333;
}

.portfolio{
 text-align: left;
 margin: 100px 40px;
 display: grid;
 grid-template-columns: repeat(auto-fill, 350px);
 justify-content: space-around;
}

.portfolio::after {
 content: '';
 flex: auto;
}

.image-with-caption{
 width: 300px;
 display: flex;
 flex-direction: column;
 align-items: center;
 text-decoration: none;
 color: black;
 transition: all .25s ease-out;
 margin:20px 50px;
}

.image-container{
 position: relative;
 height: 300px;
 width: 300px;
 overflow: hidden;
}

.image-container img{
 position: absolute;
 max-width: 120%;
 top: -9999px;
 left: -9999px;
 right: -9999px;
 bottom: -9999px;
 margin: auto;
 transition: all .45s ease-out;
}

.image-with-caption:hover img{
 max-width:100%;
 filter: none;
}

.image-with-caption:hover{
 transform: scale(1.02);
}


@media (min-width: 2500px) and (min-height: 1500px) {
 .about{ margin-top: 17%;}
 .portfolio{ margin-top: 17%;}
}

@media (max-width: 950px) {
 .midline{
  flex-direction: column;
 }
 .nav{
  text-align: center;
  margin: 10px;
 }
 .title{
  font-size:  0px;
  display: none;
 }
 .swapper {
  flex-direction: column;
  margin-top:50px;
 }
 .me-image{
  max-width: 300px;
  max-height: 300px;
 }
 .image-ball{
  height: 300px;
 }
 .about-info{
  flex-direction: column;
 }
 .about-left, .about-right{
  width: 100%;
 }
 .portfolio{
 margin: 60px 0;
 }

.image-with-caption{
 margin: 20px auto;
}
}

.v-enter-active, .v-leave-active {
 transition: all 0.3s ease-out;
}

.v-leave-to {
 opacity: 0;
 transform: translateX(80px);
}

.v-enter-from {
 transform: translateX(-80px);
 opacity: 0;
}
.footer {
 font-size: 13px;
 margin-bottom: 5px;
 color: rgba(0,0,0,0.3);
}
.small {
 font-size: 14px;
 opacity: 0.6;
}
.up-enter-active,
.up-leave-active,
.down-enter-active,
.down-leave-active {
 transition: all 0.8s ease-out;
}

.up-enter-from,
.up-leave-to {
 transform: translateY(100px);
 opacity: 0;
}

.down-slow-enter-active,
.down-slow-leave-active {
 transition: all 1.4s cubic-bezier(.47,1.64,.41,.8);
}

.down-enter-from,
.down-leave-to,
.down-slow-enter-from,
.down-slow-leave-to {
 transform: translateY(-100px);
 opacity: 0;
}
</style>
