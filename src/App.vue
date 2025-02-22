<script>
import { defineProps}from 'vue';

const myChoice = {Rock, Paper, Scissor};
const computerChoice = {Rock, Paper, Scissor};



      computerChoice = Math.floor(Math.random()*3);

      if(computerChoice === myChoice){
        return "It's a tie match!";
      }
      else if(computerChoice === Rock && myChoice === Scissor){
        return "Computer win";
      }else if(computerChoice === Scissor && myChoice === Paper){
        return "Computer win";
      }else if(computerChoice === Paper && myChoice === Rock){
        return "Computer win";
      }else{
        return "You win";
      }

</script>

<template>

</template>

<style>

</style>