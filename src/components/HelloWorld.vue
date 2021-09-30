<template>
<div class="container mt-4 mx-auto">
<div class="row d-flex justify-content-center">
  <p>{{chosenName}}</p>
  </div>
  <div class="row d-flex justify-content-center">
  <button class="btn-lg btn-primary mb-5" @click="picker">Choose!</button>
  </div>
  <div class="container">
  <div class="row mt-5 d-flex justify-content-center">
  <input class="mt-5" v-model='newGame' placeholder="Add a game to the list">
  <button class="btn btn-primary ml-2 mt-5" @click="addGame">Add a game</button>
  </div>
  <div :v-for="(game, x) in games">
  <p>
  <span class="game">{{game}}</span>   
  <button class="btn btn-danger ml-2" @click="deleteGame(x)">Delete game</button>
  </p>
  <p>{{games}}</p>
</div>  
  </div>
</div>


</template>

<script>
export default{
  data() {
      return{
      newGame: null,
      games: [],
      chosenName: 'Randomizer',
    }
  },
  mounted() {
    if(localStorage.getItem('games')){
      try{
        this.games = JSON.parse(localStorage.getItem('games'));
      }catch(e){
        localStorage.removeItem('games');
      }
    }
  },
  methods: {
    picker(){
      var chosenNumber = Math.floor(Math.random() * this.games.length);
      this.chosenName = this.games[chosenNumber];
      if (this.chosenName == null) {
        this.chosenName = 'Please add a game to the list'
      }
    },
    addGame(){
      if(!this.newGame){
        return;
      }
      this.games.push(this.newGame);
      this.newGame = '';
      this.saveGame();
    },
    deleteGame(x){
        this.games.splice(x, 1);
        this.saveGame();
    },
    saveGame(){
      const parsed = JSON.stringify(this.games);
      localStorage.setItem('games', parsed);
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
p{
  font-size: 4rem;
  text-align: center;
  color: #42A5F5;
  text-transform: uppercase;
}

button{
  border: none;
  background: #42A5F5;
  color: #fff;
  text-transform: uppercase;
  font-size: 1.5em;
  padding: 10px 20px;
  border-radius: 10px;
  cursor: pointer;
  box-shadow: 0 1px 5px rgba(#444,0.5);
  outline:none;
}</style>
