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
  <input id="game" placeholder="Add a game to the list"></div>
  <div class="row d-flex justify-content-center mt-1">
  <button class="btn btn-primary ml-2" @click="addToList">Add a game</button>
  <button class="btn btn-danger ml-2" @click="deleteList">Delete games</button>
  </div>
  <div class="row d-flex justify-content-center">
  <div>{{list}}</div>
  </div>
  </div>
</div>


</template>

<script>
export default{
  data() {
    return{
    list: ['Curse of the Dead Gods',
          'Dodgeball Academia',
          'Katamari Damacy Reroll',
          'Lumines Remastered',
          'Starmancer',
          'Art of Rally',
          'Hades',
          'Microsoft Solitaire Collection',
          'Humankind',
          'Recompile',
          'Train Sim World 2',
          'Twelve Minutes',
          'Psychonauts 2',
          'Myst',
          'Boyfriend Dungeon',
          'Library of Ruina',
          'Quake',
          'Quake II',
          'Quake III'],
    chosenName: 'Randomizer',
  }
  },
  methods: {
    picker(){
      var chosenNumber = Math.floor(Math.random() * this.list.length);
      this.chosenName = this.list[chosenNumber];
      if (this.list.length <= 0) {
        this.chosenName = 'Please add a game to the list'
      }
    },
    addToList(){
      this.list.push(document.getElementById("game").value);
    },
    deleteList(){
        for (let i = this.list.length -1; i >= 0; i--){
          this.list.splice(i, 1);
        }
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
