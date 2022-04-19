<template> 
    <div class="hero is-primary is-large">
        <div class="hero-body">
            <h1 class="title is-2" > Hi, I'm Mauricio Mahmud Sánchez </h1>
            <p class="subtitle"> ...computer scientist in progress, currently doing some Web stuff...</p>
        </div>
    </div>

        <div class="section">
            <h2 class="title size-3">Some Words about me</h2>
            <p class="subtitle">Hi, my name is Mauricio Mahmud Sánchez,</p>
            I live in Matanzas Cuba, I'm currently studing Computer Science in Havana University, <br>
            In my free time I learn new stuff that calls my atention or program something intresting (to me) (usualy in python). <br>
            Long time ago I learn basic HTML/CSS/JavaScript and I'm using it right now with Vue.js.
        </div>


    <div class="section columns">
        <Box boxTitle="Skills" class="column is-12">
                <div class="is-flex is-align-items-baseline is-flex-wrap-wrap">
                    <ExpandButton class="ml-1"  v-for="skill,i in skills" @click="changeSkillState(i)" :key="i" :title="skill.name" :text="skill.text" :isActive="skill.isActive" ></ExpandButton>
                </div>
        </Box>
    </div>
    <div class="section columns">
        <div class="column is-4">
            <Box class="" boxTitle="Skills">
                Hola
            </Box>
        </div>

        <div class="column is-4">
            <Box class="" boxTitle="Experience">
                soy 
            </Box>
        </div>

        <div class="column is-4">
            <Box class="" boxTitle="Experience">
                soy 
            </Box>
        </div>
    </div>
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
            {name:"C#", text:"My first language, used from Desktop Apps, sometimes backend dev and in some moment for game dev (Unity, Godot)", isActive:false},
            {name:"JavaScript", text:"I used in web stuff, rarely without a framework.",isActive:false},
            {name:"Vue.js", text:"It's my favorite web framework, I use it in some projects in the University.",isActive:false}
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
