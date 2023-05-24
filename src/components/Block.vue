<template>
  <p class="click" v-if="show" @click="stopTimer">click here {{score}}</p>
</template>

<script>
export default {
    name: 'BlockView',
    props:['score'],
    data(){
        return{
            show:false,
            timer:null,
            scoretwo:0
        }
    },
    mounted(){
        setTimeout(() => {
            this.show=true;
            this.startTimer()
        }, this.score);
  },
    methods:{
        startTimer(){
            this.timer=setInterval(()=>{
                this.scoretwo+=50
            },50)
        },
        stopTimer(){
            clearInterval(this.timer),
            this.$emit('endGame',this.scoretwo)
        },
    },
}
</script>

<style>
    .click{
        background-color: rgb(239, 234, 234);
        width: 300px;
        height: 300px;
    }
</style>