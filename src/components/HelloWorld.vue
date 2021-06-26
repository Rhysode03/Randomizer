<template>
<div class="container mt-4 mx-auto">
<div class="row d-flex justify-content-center">
  <p>{{chosenName}}</p>
  </div>
  <div class="row d-flex justify-content-center">
  <button class="btn-lg btn-primary" @click="picker">Choose!</button>
  </div>
</div>


</template>

<script>
export default{
  data() {
    return{
    list: ['Backbone', 'Darkest Dungeon', 'Yakuza: Like a Dragon', 'Arx Fatalis', 'Dishonored: Death of the Outsider', 'Doom (2016)', 'The Evil Within 2', 'Rage',
    'Wolfenstein II: The New Colossus', 'Fallout', 'Fallout 2', 'Fallout 3', 'Fallout Tactics', 'Worms Rumble', 'Iron Harvest', 'Need for Speed: Hot Pursuit', 'Prodeus'],
    chosenName: 'Randomizer'
  }
  },
  methods: {
    picker(){
      var chosenNumber = Math.floor(Math.random() * this.list.length);
      this.chosenName = this.list[chosenNumber];
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
