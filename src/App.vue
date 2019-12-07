<template>
<div class="text-center">
    <button @click="page='appCards'" class="btn btn-warning">Yeniden Oyna</button> <hr>
    <transition enter-active-class="animated slideInRight delay-2s" appear>
            <div>{{text}}</div>
    </transition>

<hr>
  <transition-group enter-class="" enter-active-class="animated bounceInDown" leave-active-class="" leave-class="animated bounceOutUp">
        <components key="mainComponent" :is="page"  @stat-section="page = $event"></components> 
        <canvas id="canvas" key="canvas" v-show="page=='appWinner'" ></canvas>
  </transition-group>

</div>
</template>
<script>
import cards from './components/cards'
import winner from './components/winner'
import looser from './components/looser'
export default {
components:{
    appCards:cards,
    appWinner:winner,
    appLooser:looser
},
data(){
    return{
        page:"appCards",
    text:"There's a cat in a closed box! Which one do you think shows cat in the closed box?"
    }
}
}
</script>
<style></style>
