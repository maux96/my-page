<template> 
    <div>
        <div class="hero is-primary is-large">
            <div class="hero-body">
                <h1 class="title is-2" > Hi, I'm Mauricio Mahmud</h1>
                <p class="subtitle"> ...computer scientist in progress, currently doing some Web stuff...</p>
            </div>
        </div>

        <div class="section">
            <div class="is-flex mb-4">
                <div class="mr-2">
                    <figure class="image is-64x64 ">
                        <img class="is-rounded" src="https://avatars.githubusercontent.com/u/39928836?v=4">
                    </figure> 
                </div> 
                <div>
                    <h2 class="title size-3">Some words about me</h2>
                    <p class="subtitle">Hi, my name is Mauricio Salim Mahmud Sánchez,</p>
                </div>
            </div>
            <div>
                I live in Matanzas, Cuba. I'm currently studing Computer Science in Havana University, <br>
                In my free time I learn new stuff that calls my atention or program something intresting (to me) (usualy in python). <br>
                Long time ago I learn basic HTML/CSS/JavaScript and I'm using it right now with Vue.js.
                <br>
                <div class="mt-2">
                    <a href="https://github.com/maux96">Github</a> | 
                    <a href="https://twitter.com/mauxriciom">Twitter</a> |
                    <a href="https://t.me/maux96">Telegram</a>
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
            {name:"MySql", text:"I learned in college, did some proyects, I actually use sometimes.",isActive:false},
            {name:"English/Spanish", text:"I native spanish speaker, but I can speak with others in English.",isActive:false},
        ], 
        lastSkillIndex:null,
        projects:[
            {name:"First Year College Programing Project",text: "I used C# for everything, I made an interpeter for a gived language."},
            {name:"Software Engenering",text: "We made a site for 'selling' movie tikets, we use C# and basic html/css."},
            {name:"Data Base Project",text: "We made a site to represents the interaction of a Village (Naruto Based), we used Python (Django) for the whole site."},
            {name:"Data Recovery Systems",text: "We made a Searcher call 'Gugul', the backend was made in Flask and the frontend was made in Vue.js."},
            {name:"Compilers/IA/Simulation Project",text: "We made a network simulator that use a defined language and use IA tecnics, was made in C#."},

        ]
    } 
  }, 
  methods:{
      changeSkillState(index){
            if(this.lastSkillIndex == index){
                this.skills[index].isActive=!this.skills[index].isActive;
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
    document.title="maux96"
  }
}
</script>

<style>
    @import 'bulma/css/bulma.css';
</style>
