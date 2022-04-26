<template>
    <div class="has-background-primary is-short expand-button is-white" :class="{'has-background-success':isActive}" >
        <p class="expand-button-title">{{title}}</p>

        <transition name="fade">
          <div v-if="isActive" class="notification description is-success">{{text}}</div>
        </transition>
    </div>
</template>

<script>
export default {
  name: 'ExpandButton',
  props: {
    title: String,
    text: String,
    isActive: Boolean 
  },
  data(){
    return {
    }
  },
  
}


</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
    .expand-button-title{
      font-weight: bolder;
      color: white;
    }
    .expand-button{
      transition: all 0.3s;
      padding:10px;
      padding-left: 30px;
      padding-right: 30px;
      border-radius: 5px;
      position: relative;
    }   
    .description{
      position: absolute;
      left: 0;
      width:200%;
      z-index: 10;
    }  

    .fade-enter-from, .fade-leave-to{
      transform: translateY(-10px);
      opacity: 0;
    }
    .fade-leave-from, .fade-enter-to{
      opacity: 1;
    }
    .fade-enter-active, .fade-leave-active{
      transition: all 0.3s;
    }
</style>
