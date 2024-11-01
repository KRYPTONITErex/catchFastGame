<template>
  <div class="block" v-if="showBlock" @click="stopTimer">Click HERE {{ delay }}</div>

  <!-- <p>RESULT IS {{ score }}</p> -->
</template>

<script>
export default {
    props: ['delay'],
    data(){
        return{
            showBlock:false,
            score:0,
            timer:null
        }
    },
    mounted(){
        setTimeout(() => {
            this.showBlock=true;
            this.startTimer()
        }, this.delay);
    },
    methods: {
        startTimer(){
            this.timer=setInterval(()=>{
                this.score+=50;
            },50);
        },
        stopTimer(){
            clearInterval(this.timer);
            console.log(this.score);
            this.$emit("endGame",this.score)
        }
    }

    // updated(){
    //     console.log("data updated");
    // },
    // unmounted(){
    //     console.log("component unmounted")
    // }

}
</script>

<style>
.block{
    background-color: rgb(137, 238, 238);
    width: 400px;
    height: 300px;
    margin: 20px auto;
    padding-top: 30px;
    border-radius: 10px;
    box-shadow: 8px 8px 3px grey;
}
</style>