<template> 
    <div class="hero is-primary is-large">
        <div class="hero-body">
            <h1 class="title is-2" > Hi, I'm Mauricio Mahmud</h1>
            <p class="subtitle"> ...computer scientist in progress, currently doing some Web stuff...</p>
        </div>
    </div>

    <div class="section">
        <div class="columns">
            <div class="column is-1">
                <figure class="image is-64x64 ">
                    <img class="is-rounded" src="https://avatars.githubusercontent.com/u/39928836?v=4">
                </figure> 
            </div> 
            <div class="column">
                <h2 class="title size-3">Some Words about me</h2>
                <p class="subtitle">Hi, my name is Mauricio Salim Mahmud Sánchez,</p>
            </div>
        </div>
        <div>
            I live in Matanzas Cuba, I'm currently studing Computer Science in Havana University, <br>
            In my free time I learn new stuff that calls my atention or program something intresting (to me) (usualy in python). <br>
            Long time ago I learn basic HTML/CSS/JavaScript and I'm using it right now with Vue.js.
            <br>
            <div class="mt-2">
                <a href="https://github.com/maux96">Github</a> | 
                <a href="https://twitter.com/mauxriciom">Twitter</a>
            </div>
        </div>
    </div>
    <hr>  
    <div class="section">
        <div class="columns">
            <div class="column is-4">
                <div class="is-flex is-align-items-baseline">
                    <h2 class="title size-3">Skills </h2><p class="has-text-primary">click it!</p>
                </div>
                <div class="is-flex is-align-items-baseline is-flex-wrap-wrap">
                <ExpandButton class="ml-1 mb-1"  v-for="skill,i in skills" @click="changeSkillState(i)" :key="i" :title="skill.name" :text="skill.text" :isActive="skill.isActive" ></ExpandButton>
                </div>
            </div>
            <div class="column is-4" >
                <h2 class="title size-3">Interests</h2>
                <div>
                    ComputerScience, AI, MachineLearning, Maths, Blockchain and Crypto, GameDev, Linux, VIM and more.
                </div> 
            </div>
            <div class="column is-4" >
                <h2 class="title size-3">Experience</h2>
                <div>
                    Lorem ipsum dolor sit amet consectetur adipisicing elit. Odit ad veritatis doloribus nulla autem sequi rerum molestias iure iste saepe quibusdam, voluptate amet, similique enim, neque adipisci optio facere harum! 
                </div> 
            </div>
        </div>
    </div>

    <footer class="footer is-primary">
  <div class="content has-text-centered">
      <p>Mauricio Salim Mahmud Sánchez</p>
    <p>
      <a href="https://github.com">Github</a>
        |
      <a href="https://twitter.com/mauxriciom">Twitter</a>
    </p>
  </div>
</footer>

</template>		


<script>
import ExpandButton from './components/expandButton.vue'
import Box from './components/box.vue'
export default {
  name: 'App',
  data(){
    return {
        skills: [
            {name:"Python", text:" Probably my most used lenguage right now, every day for the most simple tasks, automatization, math stuff, machine learning, backend (Django, Flask), web-scrapping and whatever I need to do fast.", isActive:false},
            {name:"C#", text:"My first language, used from Desktop Apps, sometimes backend dev and in some moment for game dev (Unity, Godot).", isActive:false},
            {name:"C", text:"I used it in Operative System course, did several projects oriented to linux.", isActive:false},
            {name:"JavaScript", text:"I used it in web stuff, rarely without a framework.",isActive:false},
            {name:"Vue.js", text:"It's my favorite web framework, I used it in some projects in the University.",isActive:false},
            {name:"Git", text:"I learned in university, actually I use it for everything.",isActive:false},
            {name:"MySql", text:"I learned in university, I actually use sometimes.",isActive:false},
        ], 
        lastIndex:null
    } 
  }, 
  methods:{
      changeSkillState(index){
            if(this.lastIndex == index){
                this.skills[index].isActive=!this.skills[index].isActive;
            }else{
                this.skills[index].isActive=true;
                if(this.lastIndex!=null)
                    this.skills[this.lastIndex].isActive=false;
                this.lastIndex=index;
            }
      }
  },
  components: {
    ExpandButton,
    Box
  }
}
</script>

<style>
    @import 'bulma/css/bulma.css';
</style>
