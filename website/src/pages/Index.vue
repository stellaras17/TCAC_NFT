<template>
  <q-page class="flex flex-center">

   <q-header bordered class="bg-white text-white" height-hint="98">
      <q-toolbar style="min-height: 55px;" >
        <q-toolbar-title class="text-primary">
          <q-avatar color="primary">
            <img src="../assets/logo.jpg">
          </q-avatar>
          The Crazy Avocado Club
        </q-toolbar-title>
        <div class="row">
              <q-btn flat target="_blank" href="https://twitter.com/TCAC_Official" class="q-pa-lg" size="xl" color="black" icon="fab fa-twitter" />
              <q-btn flat target="_blank" href="https://discord.gg/vXw9u2XwQ6" class="q-pa-lg" size="xl" color="black" icon="fab fa-discord" />
            </div>
      </q-toolbar>

      <nav @click="getScroll" class="navbar">
        <div class="container">
          <ul>
            <li class="mint"><p class="cursor-pointer" @click="scrollMeTo('mint')">MINT</p></li>
            <li class="about"><p class="cursor-pointer" @click="scrollMeTo('about')">ABOUT</p></li>
            <li class="environment"><p class="cursor-pointer" @click="scrollMeTo('environment')">ENVIRONMENT</p></li>
            <li class="roadmap"><p class="cursor-pointer" @click="scrollMeTo('roadmap')">ROADMAP</p></li>
            <li class="team"><p class="cursor-pointer" @click="scrollMeTo('team')">TEAM</p></li>
            <li class="faq"><p class="cursor-pointer" @click="scrollMeTo('faq')">FAQ</p></li>
            <!-- <q-btn size="20px" color="yellow-11" class="text-black" to="/youravocados">YOUR AVOCADOS</q-btn> -->
          </ul>

        </div>
      </nav>

      
    </q-header>
    
    <div class="column flex flex-center">
      <section style="width:100%" ref="mint" id="mint" >
        <q-banner style="width:100%;" class="flex flex-center text-white bg-red">
      <p style="margin: 0 auto; text-align:center">Minting starts on 26 Feb, 2022 17:00 UTC</p>
    </q-banner>
        <mint/>
      </section>
      <section style="width:100%" ref="about" id="about" >
        <about/>
      </section>
      <section style="width:100%" ref="environment" id="environment" >
        <environment/>
      </section>
      <section style="width:100%" ref="roadmap" id="roadmap">
        <roadmap/>
      </section>
      <section style="width:100%" ref="team" id="team">
        <team/>
      </section>
      <section style="width:100%" ref="faq" id="faq">
        <faq/>
      </section>
    </div>
  
    <div class="floating-avos">
      <img src="../assets/bg/ba.png" alt="">
      <img src="../assets/bg/hba.png" alt="">
      <img src="../assets/bg/pa.png" alt="">
      <img src="../assets/bg/ba.png" alt="">
      <img src="../assets/bg/hba.png" alt="">
      <img src="../assets/bg/pa.png" alt="">
    </div>


    <footer class="footer q-mt-xl">
        <div class="container-footer footer-line">
          <hr class="line" />
          <div class="row flex flex-center" style="width:100%; overflow: hidden">
            <q-space/>
            <q-space/>
            <div class="row">
              <q-btn flat target="_blank" href="https://twitter.com/TCAC_Official" class="footer-icon q-pa-lg" size="lg" color="black" icon="fab fa-twitter" />
              <q-btn flat target="_blank" href="https://discord.gg/vXw9u2XwQ6" class="footer-icon q-pa-lg" size="lg" color="black" icon="fab fa-discord" />
            </div>
            <q-space/>
            <q-img @click="scrollMeTo('mint')" class="q-ma-md q-pa-md logo" src="../assets/logo.jpg" alt="" />
            <q-space/>
            <div class="row">
              <q-btn flat target="_blank" href="https://www.tiktok.com/@thecrazyavocadoclub" class="footer-icon q-pa-lg" size="lg" color="black" icon="fab fa-tiktok" />
              <q-btn flat target="_blank" href="https://www.instagram.com/thecrazyavocadoclub/" class="footer-icon q-pa-lg" size="lg" color="black" icon="fab fa-instagram" />
            </div>
            <q-space/>
            <q-space/>
          </div>
        </div>
      </footer>
    
  </q-page>
</template>

<script>
import { defineComponent, Vue } from 'vue';



export default {
  data() {
    return {
      
    }
  },
  components: {
    'mint': require('components/mint.vue').default,
    'about': require('components/about.vue').default,
    'environment': require('components/environment.vue').default,
    'roadmap': require('components/roadmap.vue').default,
    'team': require('components/team.vue').default,
    'faq': require('components/faq.vue').default,
  },
  methods: {
    logSects() {
      console.log(sections);
    },
    initiateActive(){
      const navLi = document.querySelectorAll('nav .container ul li')
      navLi.forEach(li => {
          if(li.classList.contains('mint')){
            li.classList.add('active')
          }
        })
    },
    getScroll() {
      const sections = document.querySelectorAll('section');
      const navLi = document.querySelectorAll('nav .container ul li')

      window.addEventListener('scroll', ()=> {
      let current ='';
        sections.forEach( section => {
          const sectionTop = section.offsetTop;
          const sectionHeight = section.clientHeight;
          if(pageYOffset >= sectionTop){
            current = section.getAttribute('id')
          }
        })
        navLi.forEach(li => {
          li.classList.remove('active')
          if(li.classList.contains(current)){
            li.classList.add('active')
          }
        })
      })
    },
    scrollMeTo(refName) {
      var element = this.$refs[refName];
      var top = element.offsetTop;

      window.scrollTo({top:top, behavior: 'smooth'});
    }
  },
  mounted() {
    this.initiateActive()
    this.getScroll()
  }
}

</script>

<style lang="css" scoped>
 .q-page{
  background-color: rgb(173, 238, 69);
  /* background-color: rgb(208, 255, 133); */
  background-size: cover;

} 
nav {
  position: sticky;
  top: 0;
  background-color: black;
}
nav .container {
  width: 100%;
  max-width: 1000px;
  margin: 0 auto;
  text-align: center;
  padding: 5px;
}
nav .container ul {
  list-style: none;
  font-size: 24px;
  
}
nav .container ul li{
  display: inline-block;
  
}
nav .container ul li p{
  font-family: "Lucida Console";
  font-weight: bold;
  display: inline-block;
  padding: 10px 20px;
  color: #fffdf0;
  text-decoration: none;
}
p{
  font-family: "Lucida Console";
  font-weight: bold;
  color: #fffdf0;
  text-decoration: none;
}
.q-btn{
  font-family: "Lucida Console";
  font-weight: 500;
  color: #fffdf0;
  text-decoration: none;
}
nav .container ul li.active p{
  color: #FFFFA7;
  text-decoration-line: underline !important;
  text-decoration-thickness: 10px;
  transition: 0.3 ease text-decoration;

}
.footer{
  bottom: 0;
  width: 100%;
}
.container-footer{
  background-color: #ffffff;
  width: 100%;
  padding-right: 15px;
  padding-left: 15px;
  margin-right: auto;
  margin-left: auto;
}
.line{
  padding: 0 !important;
}
.q-toolbar__title{
  font-size: 38px;
  font-family: "Lucida Console";
  font-weight: 900;
}
.logo {
  height: 200px;
  width: 220px;
}

.floating-avos img{
  width: 150px;
  animation: avos 30s linear infinite;
}
.floating-avos{
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-around;
  position: absolute;
  top: -220px;
}

.floating-avos img:nth-child(1){
  animation-delay: 16s;
  width: 200px;
}
.floating-avos img:nth-child(2){
  animation-delay: 24s;
}
.floating-avos img:nth-child(3){
  animation-delay: 2s;
  width: 220px;
}
.floating-avos img:nth-child(4){
  animation-delay: 8.5s;
}
.floating-avos img:nth-child(5){
  animation-delay: 22s;
  width: 180px;
}
.floating-avos img:nth-child(6){
  animation-delay: 17s;
  width: 130px;
}


@keyframes avos {
  0%{
    transform: translateY(0);
    opacity: 0;
  }
  5%{
    opacity: 1;
  }
  90%{
    opacity: 1;
  }
  100%{
    transform: translateY(540vh);
    opacity: 0;
  }
}

@media screen and (max-width: 768px){
  .logo {
    height:55px; width:70px
  }
  .navbar {
    display: none;
  }
  .footer-icon {
    width: 10px !important;
  }
  i::before {
    width: 10px !important;
  }
  .floating-avos img:nth-child(1){
  display: none;
  }
  .floating-avos img:nth-child(2){
  display: none;
  }
  .floating-avos img:nth-child(5){
  display: none;
  }
  .floating-avos img:nth-child(6){
  display: none;
  }
}
</style>
