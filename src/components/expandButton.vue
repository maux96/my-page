<template>
    <div class="notification is-primary is-short my-anim" :class="{'is-success':isActive}" >
        <p><strong>{{title}}</strong></p>

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
    .my-anim{
	    transition: all 0.3s;
    }   
    .description{
      position: absolute;
      width:200%;
      z-index: 10;
    }  
    .fade-enter-from, .fade-leave-to{
      opacity: 0;
    }
    .fade-leave-from, .fade-enter-to{
      opacity: 1;
    }
    .fade-enter-active, .fade-leave-active{
      transition: opacity 0.3s;
    }
</style>
