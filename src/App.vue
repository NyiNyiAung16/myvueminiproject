<template>
  <div class="main">
    <h2>Can you catch me?</h2>
    <button class="play" @click="start" :disabled="disappear">play</button>
    <div v-if="bs">
    <Block :score="this.score" @endGame="endGame"/>
    </div>
    <div v-if="result">
    <Result :scoreResult="this.scoretwo"/>
    </div>
    <p class="text">I am looking forward to happy by using my app</p>
  </div>
</template>

<script>
import Block from "./components/Block.vue"
import Result from "./components/Result.vue"
export default {
  components:{
    Block,
    Result
  },
  data(){
    return{
      bs:false,
      disappear:false,
      score:0,
      result:false,
      scoretwo:0
    }
  },
  methods:{
    start(){
      this.bs=true,
      this.disappear=true,
      this.score=1000+Math.random()*3000
    },
    endGame(score){
      this.scoretwo=score,
      this.bs=false,
      this.disappear=false,
      this.result=true
    }
  },
  mounted(){
        setTimeout(() => {
            this.bs
        }, this.score);
  },
  
}
</script>
  
<style>
  .main{
    display:flex;
    flex-direction: column;
    align-items: center;
  }
  h2{
    color: rgb(24, 247, 106);
  }
  .play{
    border: 1px solid rgb(155, 155, 155);
    border-radius: 4px;
    background-color: rgb(73, 236, 55);
  }
  .text{
    color: rgb(237, 14, 14);
  }
</style>