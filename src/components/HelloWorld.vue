<template>
  <div class="hello">
  <div class="gamers">
    <div class="gamer">
    <h1>SEN</h1>
    <div class="gamerNumberOfLives"><h2>%100</h2></div>
  </div>
  <div class="monster">
    <h1>CANAVAR</h1>
    <div class="monsterNumberOfLives"><h2>%100</h2></div>
  </div>
  </div>
  <div class="buttons">
    <button class="attack">Saldırı</button>
    <button class="specialAttack" >Özel Saldırı</button>
    <button class="firstAid">İlk yardım</button>
    <button class="giveUp">Pes Et</button>
  </div>
  <div class="log">
    <h3 class="logsText">Logs</h3>
    <div class="result">
    <div class="gamerResut">
      <h3>Canavarın canının azalttın (8)</h3>
    </div>
    <div class="monsterResult">
      <h3>Canavarın saldırısı (5)</h3>
    </div>
  </div>
  
</div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  data(){
    return{
      caount:0
    }
  },
  props: {
    msg: String
  }
}
</script>
<style>
.gamers{
  display: flex;
  justify-content: center;
  align-items: center;
}
.gamer{
  padding-right: 8rem;
}
.gamerNumberOfLives{
  width: 20rem;
  background-color: green;
}
.monsterNumberOfLives{
  width: 20rem;
  background-color: green;
}
.buttons{
  background-color: white;
  border:1px solid gray;
  position: relative;
  margin: auto;
  width: 48rem;
  border-radius: 5px;
  margin-bottom: 3rem;
}
button{
  margin: 2rem 2rem 2rem 2rem;
  width: 5rem;
  height: 3rem;
  border-radius: 10px;
  color: white;
  font-weight: bold;
}
.attack{
  background-color: red;
}
.specialAttack{
  background-color: orange;
}
.firstAid{
  background-color: rgb(45, 194, 45);
}
.giveUp{
  border: 1px solid gray;
  background-color: white;
  color: black;
}
.log{
  border-radius: 10px;
  position: relative;
  margin: auto;
  background-color: white;
  border: 1px solid gray;
  width: 48rem;
}
.logsText{
  color: blue;
}
.result{
  position: relative;
  margin: auto;
  width: 45rem;
  border: 1px solid black;
  background-color: rgb(213, 203, 203);
  margin-bottom: 2rem;
}
.gamerResut{
  color: black;
  background-color: rgb(190, 221, 190);
  border: 1px solid gray;
}

</style>

