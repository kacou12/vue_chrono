<template>
<div>
    <input type="text" id="affich" :value="calcul"><br>
    <button @click="number">0</button>
    <button @click="number">1</button>
    <button @click="number">2</button><br>
    <button @click="number">3</button>
    <button @click="number">4</button>
    <button @click="number">5</button><br>
    <button @click="number">6</button>
    <button @click="number">7</button>
    <button @click="number">8</button><br>
    <button @click="number">9</button>
    <button @click="operator" v-bind:disabled="btnDisable">+</button>
    <button @click="operator"  v-bind:disabled="btnDisable">-</button><br>
    <button @click="operator"  v-bind:disabled="btnDisable">*</button>
    <button @click="operator"  v-bind:disabled="btnDisable">/</button>
    <button @click="egale" v-bind:disabled="btnDisable">=</button><br>
    <button @click="supp" v-bind:disabled="btnDisable">suppri</button>
    <button @click="clean">clean</button>
</div>
  
</template>

<script>
export default {
    data() {
        return {calcul : '', btnDisable:true}
    },
    methods :{
        number: function (el){
            console.log(el.target.innerHTML)
            this.calcul += el.target.innerHTML
            this.btnDisable = false
        },
        operator: function(signe){
            this.calcul += signe.target.innerHTML
            this.btnDisable = true
        },
        egale: function(){
            this.calcul = eval(this.calcul)
            this.calcul = this.calcul.toString()
            this.btnDisable = true
        },
        supp: function(){
            this.calcul = this.calcul.slice(0, -1)
        },
        clean: function(){
            this.calcul = ''
        }
    }
}
</script>

<style>

</style>