<script setup>
import {ref} from 'vue'

const noBtn = ref(false)

const handleNoClick = () => {
    return noBtn.value = true
};

const yesBtn = ref(false)

// const getNoButtonText = () => {
//     const phrases = [
//       "No",
//       "Are you sure?",
//       "Really sure?",
//       "Think again!",
//       "Last chance!",
//       "Surely not?",
//       "You might regret this!",
//       "Give it another thought!",
//       "Are you absolutely certain?",
//       "This could be a mistake!",
//       "Have a heart!",
//       "Don't be so cold!",
//       "Change of heart?",
//       "Wouldn't you reconsider?",
//       "Is that your final answer?",
//       "You're breaking my heart ;(",
//     ];

//     return phrases[Math.min(noCount, phrases.length - 1)];
//   };


</script>
<template>
  <div class="screen">
    <img :src="yesBtn ? 'https://media.tenor.com/gUiu1zyxfzYAAAAi/bear-kiss-bear-kisses.gif' : 'https://gifdb.com/images/high/cute-love-bear-roses-ou7zho5oosxnpo6k.gif'" alt="">
    <h1>{{ yesBtn ? "I love You Too 😽" : "Will you be my Valentine?" }}</h1>
    <div class="group-btn" v-if="yesBtn == false">
      <button class="btn btn-yes"
       @click="yesBtn = true"
      >
        {{ noBtn ? "There only Yes 😼❤️" : "Yes" }}
      </button>
      <button class="btn btn-no" 
        :class="{ 'd-none':noBtn }"
        @click="handleNoClick"
        >
        No
      </button>
    </div>
    <div class="group-btn" v-else>
      <h1>Brab Vid Vid hx >-&lt; </h1>
    </div>
  </div>
</template>
<style scoped>
  .screen {
    min-width: 100%;
    flex-direction: column;
    max-width: 100%;
    background-color: white;
    height: 100vh;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
  }
  .d-none{
    display: none;
  }
  .screen h1{
    color: black;
  }
  .screen img{
    width: 20%;
    margin: 0 auto;
  }
  .group-btn{
    margin-top: 26px;
    display: flex;
    gap: 20px;
  }
  .btn{
    padding: 10px 30px;
    font-family: sans-serif;
    border: 0px;
    border-radius: 7px;
    color: white;
    font-weight: bold;
    font-size: 20px;
  }
  .btn-yes{
    background-color: rgb(0, 233, 12);
  }
  .btn-no{
    background-color: red;
  }
  @media (min-width: 320px) and (max-width: 425px) {
    .screen img{
      width: 50%;
    }
    .screen h1{
      font-size: 19px;
    }
  }
</style>