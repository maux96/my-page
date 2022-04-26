<template>
    <div>
        <div class="blocker-for-skill" v-if="lastSkillIndex!=null" @click="changeSkillState(lastSkillIndex)"></div>
            <div class="hero is-primary p-6" :class="{ 'is-medium' : !_isInitial.banner_picture || !_isInitial.banner_title || !_isInitial.banner_subtitle || !_isInitial.banner_texts}"   >
                <div class="hero-body"> 
                    <div class="is-flex mb-4 is-flex-wrap-wrap is-align-items-center" >
                        <div class="mr-2">
                            <transition name="grow">
                                <figure v-if="_isInitial.banner_picture" class="image is-64x64 ">
                                    <img class="is-rounded" src="https://avatars.githubusercontent.com/u/39928836?v=4">
                                </figure> 
                            </transition>
                        </div> 
                        <div>
                            <transition-group name="grow">
                                <h1 v-if="_isInitial.banner_title" class="title is-2" > Hi, I'm Mauricio Mahmud</h1>
                                    <p v-if="_isInitial.banner_subtitle" class="subtitle"> ...computer scientist in progress, currently doing some Web stuff... </p>
                                    
                            </transition-group>
                        </div>
                    </div>
                    <div>
                        <transition name="grow">
                            <div v-if="_isInitial.banner_texts">
                                I live in Matanzas, Cuba. I'm currently studing Computer Science in Havana University, <br>
                                In my free time I learn new stuff that calls my atention or program something intresting. <br>
                                Long time ago I learned basic HTML/CSS/JavaScript and I'm using it right now with Vue.js.
                            </div>
                        </transition>
                        <br>
                        <div class="mt-2">
                            <transition-group name="grow">
                                <div v-if="_isInitial.banner_texts">
                                    <a href="https://github.com/maux96">Github</a> |  
                                    <a href="https://twitter.com/mauxriciom">Twitter</a> |
                                    <a href="https://t.me/maux96">Telegram</a>
                                </div>
                            </transition-group>
                       </div>
                    </div>
                
                </div>


            </div>

        <div class="section">
            <div class="columns">
                <div class="column is-4">
                    <div class="is-flex is-align-items-baseline">
                        <h2 class="title size-3">Skills </h2> <p class="has-text-primary ml-2">click it!</p>
                    </div>
                    <div class="is-flex is-align-items-baseline is-flex-wrap-wrap">
                    <ExpandButton class="ml-1 mb-1"  v-for="skill,i in skills" @click="changeSkillState(i)" :key="i" :title="skill.name" :text="skill.text" :isActive="skill.isActive" ></ExpandButton>
                    </div>
                </div>
                
                <div class="column is-4" >
                    <h2 class="title size-3">Projects made </h2>
                    <div>
                        <ul>
                            <li v-for="p,i in projects" :key="i" ><strong>{{p.name}}: </strong>{{ p.text }}</li>
                        </ul>
                    </div> 
                </div>

                <div class="column is-4" >
                    <h2 class="title size-3">Interests</h2>
                    <div>
                        ComputerScience, AI, MachineLearning, Maths, Blockchain and Crypto, GameDev, Linux, VIM and more.
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
            |
          <a href="https://t.me/maux96">Telegram</a>
        </p>
      </div>
    </footer>
    </div>
</template>		


<script>
import ExpandButton from './components/expandButton.vue'

export default {
  name: 'App',
  data(){
    return {
        skills: [
            {name:"Python", text:" Probably my most used lenguage right now, every day for the most simple tasks, automatization, math stuff, machine learning, backend (Django, Flask), web-scrapping and whatever I need to do fast.", isActive:false},
            {name:"C#", text:"My first language, used for Desktop Apps, sometimes backend dev and ,in some moment, for game dev (Unity, Godot).", isActive:false},
            {name:"C", text:"I used it in Operative System course, did several projects oriented to linux.", isActive:false},
            {name:"JavaScript", text:"I used it in web stuff, rarely without a framework.",isActive:false},
            {name:"Vue.js", text:"It's my favorite web framework, I used it in some projects in my career.",isActive:false},
            {name:"Git", text:"I learned in my career, actually I use it for everything.",isActive:false},
            {name:"Maths", text:"I'm studing Computer Science, I learned a lot in my career, this helps me with the little bit complicated problems.",isActive:false},
            {name:"Sql", text:"I learned in college, did some proyects, I actually use sometimes.",isActive:false},
            {name:"English/Spanish", text:"I am native spanish speaker, but I can comunicate with others in English, read, write and understand bibliography.",isActive:false},
        ], 
        lastSkillIndex:null,
        projects:[
            {name:"First Year College Programing Project",text: "I used C# for everything, I made an interpreter for a given language."},
            {name:"Software Engenering",text: "We made a site for 'selling' movie tikets, we use C#, basic html/css and MySql data base."},
            {name:"Data Base Project",text: "We made a site to represents the interaction of a Village (Naruto Based), we used Python (Django) for the whole site and MySql data base."},
            {name:"Data Recovery Systems",text: "We made a Searcher call 'Gugul', the backend was made in Flask and the frontend was made in Vue.js."},
            {name:"Compilers/IA/Simulation Project",text: "We made a network simulator that use a defined language and use IA tecnics, was made in C#."},

        ],
        _isInitial:{}, //for animation :D
    } 
  }, 
  methods:{
      changeSkillState(index){
            if(this.lastSkillIndex == index){
                this.skills[index].isActive=false;
		this.lastSkillIndex=null;
            }else{
                this.skills[index].isActive=true;
                if(this.lastSkillIndex!=null)
                    this.skills[this.lastSkillIndex].isActive=false;
                this.lastSkillIndex=index;
            }
      },
  },
  components: {
    ExpandButton,
  },
  mounted(){
    document.title="maux96";
    let temp = this;


    setTimeout(function(){
        temp._isInitial.banner_picture = true;
    }, 500);

    setTimeout(function(){
        temp._isInitial.banner_title = true;
    }, 700);
    setTimeout(function(){
        temp._isInitial.banner_subtitle = true;
    }, 900);
    setTimeout(function(){
        temp._isInitial.banner_texts = true;
    }, 1000);

  }
}
</script>

<style>
    @import 'bulma/css/bulma.css';

    .blocker-for-skill{
        top:0px;
        left:0px;
        width:100%;	
        height:100%;
        /*background-color:red;*/
        position:fixed;
    }

    .grow-enter-from{
        opacity:0;
        transform: translateY(50px); 
    }
    .grow-enter-to{
        opacity:1;
    }
    .grow-enter-active{
        transition: all 0.8s;
    }
</style>




