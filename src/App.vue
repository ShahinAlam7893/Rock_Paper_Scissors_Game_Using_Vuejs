<script setup>
import { ref } from 'vue';


const choices = ["Rock", "Paper", "Scissors"];



const playerChoice = ref("None");
const computerChoice = ref("None");
const result = ref("");



const determineWinner = (player, computer) => {
    if (player === computer) {
        return "It's a Tie!";
    }
    if (
        (player === "Rock" && computer === "Scissors") ||
        (player === "Scissors" && computer === "Paper") ||
        (player === "Paper" && computer === "Rock")
    ) {
        return "You Win!";
    }
    return "You Lose!";
};


const playGame = (choice) => {
    playerChoice.value = choice;
    computerChoice.value = choices[Math.floor(Math.random() * choices.length)];
    result.value = determineWinner(playerChoice.value, computerChoice.value);
};
</script>

<template>
    <div>
        <h2>Rock, Paper, Scissors</h2>
        <div>
            <button v-for="choice in choices" :key="choice" @click="playGame(choice)">
                {{ choice }}
            </button>
        </div>

        <p>Your Choice:
            <span class="choice-text">{{ playerChoice }}</span>
        </p>

        <p>Computer's Choice:
            <span class="choice-text">{{ computerChoice }}</span>
        </p>

        <h3>{{ result }}</h3>
    </div>
</template>

<style scoped>
:root {
  font-family: Inter, system-ui, Avenir, Helvetica, Arial, sans-serif;
  line-height: 1.5;
  color-scheme: light dark;
  color: rgba(255, 255, 255, 0.87);
  background-color: #242424;
}

body {
  margin: 0;
  display: flex;
  place-items: center;
  min-height: 100vh;
}
h2{
  text-align: center;
  text-decoration: underline;
}

button {
  border-radius: 8px;
  border: 2px solid transparent;
  padding: 0.8em 1.4em;
  margin: 2px;
  font-size: 1em;
  font-weight: 500;
  font-family: inherit;
  color: aliceblue;
  background-color: #1a1a1a;
  cursor: pointer;
  transition: border-color 0.25s;
}
button:hover {
  border-color: #646cff;
}
button:focus,
button:focus-visible {
  outline: 4px auto -webkit-focus-ring-color;
}
p{
  text-align: center;
}

#app {
  max-width: 100%;
  margin: 0 auto;
  text-align: center;
}
</style>
