<template>
  <section>
    <p>Play the game</p>

    <div v-if="isLoggedIn" id="logout">

        <h1>
          <i class="fa fa-2x fa-fw" v-bind:class="computedUser">{{userPick}}</i>
           - 
          <i class="fa fa-2x fa-fw" v-bind:class="computedRand">{{randPick}}</i>
        </h1>

        <div>
          <button @click="choose('rock')">
            <i class="fa fa-hand-rock-o">Rock</i>
          </button>

          <button @click="choose('paper')">
            <i class="fa fa-hand-paper-o">Paper</i>
          </button>
          <button @click="choose('scissors')">
              <i class="fa fa-hand-scissors-o">Scissors</i>
          </button>
        </div>
        <h1>{{ userScore }} - {{ computerScore }}</h1>

    </div>
    <p v-else>
      <span><a href="/register">Register</a></span>
      <span> or </span>
      <span><a href="/login">Log In</a></span>
    </p>
  </section>
</template>
<script>

export default {
  name: 'Home',
  computed : {
    isLoggedIn: function() {
      return this.$store.getters.isAuthenticated;
    },
    computedUser: function () {
      return {
        "fa-circle-o-notch fa-spin": this.userPick === null,
        "fa-hand-rock-o": this.userPick === "rock",
        "fa-hand-paper-o": this.userPick === "paper",
        "fa-hand-scissors-o": this.userPick === "scissors"
      };
    },
    computedRand: function () {
      return {
        "fa-circle-o-notch fa-spin": this.randPick === null,
        "fa-hand-rock-o": this.randPick === "rock",
        "fa-hand-paper-o": this.randPick === "paper",
        "fa-hand-scissors-o": this.randPick === "scissors"
      };
    }
  },
  data: function () {
    return {
      userPick: null,
      randPick: null,
      userScore: 0,
      computerScore: 0
    };
  },
  methods: {
    choose: function (pick) {
      this.userPick = pick;
      const picks = ['rock', 'paper', 'scissors'];
      this.randPick = picks[Math.floor(Math.random() * picks.length)];
      this.setScore();
    },
    setScore: function () {
      if (this.userPick == 'rock') {
        if (this.randPick == 'paper') {
          console.log('Computer wins');
          this.computerScore++;
        } else if (this.randPick == 'scissors') {
          console.log('User wins');
          this.userScore++;
        } else {
          console.log('Draw');
        }
      } else if (this.userPick == 'paper') {
        if (this.randPick == 'rock') {
          console.log('User wins');
          this.userScore++;
        } else if (this.randPick == 'scissors') {
          console.log('Computer wins');
          this.computerScore++;
        } else {
          console.log('Draw');
        }
      } else {
        if (this.randPick == 'rock') {
          console.log('Computer wins');
          this.computerScore++;
        } else if (this.randPick == 'paper') {
          console.log('User wins');
          this.userScore++;
        } else {
          console.log('Draw');
        }
      }
    }
  },
}

</script>