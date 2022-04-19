<template>
    <div class="box">
        <h3 class="title is-3">{{boxTitle}}</h3>
        <div>
          <slot></slot>
        </div>
    </div>
</template>

<script>
    export default {
      name: 'Box',
      props:{
        boxTitle:String
      },
      data(){
        return {
        }
      },
    }
</script>
