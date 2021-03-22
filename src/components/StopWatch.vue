<template>
  <div>
    <button type="button"  v-bind:disabled="btnDisable" @click="start"> start </button>
      <span> {{ heure }} : {{ minute }} : {{  seconde }}</span>
    <button type="button" @click="stop"> stop </button>
    <button type="button" @click="reset"> reset </button>
</div>
</template>

<script>
    export default {
        data(){
           return {
            seconde : 0,
            minute: 0,
            heure: 0,
            id_time: null,
            btnDisable : false
            }
        },
    watch: {
        seconde: function(newval){
            //console.log(newval)
            if(newval == 60){
                this.minute += 1
                this.seconde = 0
            }

  
        },
        minute: function(newval){
            //console.log(newval)
            if(newval == 60){
                this.heure += 1
                this.minute = 0
                alert("Sa fait maintenant "+ this.heure+ " heures")
            }
  
        }
    },
     methods :{
        stop: function (){
           clearInterval(this.id_time)
           this.btnDisable = false 
        },
        start (){
            //console.log('ici')
                this.id_time = setInterval( () =>{
                    this.seconde += 1
                }, 1000)
                this.btnDisable = true            
          
        },
        reset: function (){
            this.seconde = 0
            this.minute = 0
            this.heure = 0
            this.stop()
        },
     }
    }
</script>

<style>

</style>