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
