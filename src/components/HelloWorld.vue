<template>
  <div class="hello">
  <div class="gamers">
    <div class="gamer">
    <h1>SEN</h1>
    <div class="gamerNumberOfLives" :style="{'background-color': gamerNumberOfLives>70 ? '#00FF00':(gamerNumberOfLives>30 ? 'yellow' :  'red')}"><h2>%{{gamerNumberOfLives}}</h2></div>
  </div>
  <div class="monster">
    <h1>CANAVAR</h1>
    <div class="monsterNumberOfLives" :style="{'background-color': monsterNumberOfLives>70 ? '#00FF00':(monsterNumberOfLives>30 ? 'yellow' :  'red')}"><h2>%{{monsterNumberOfLives}}</h2></div>
  </div>
  </div>
  <div class="buttons">
    <button class="attack" v-if="gamerNumberOfLives!=0" @click="attack('attack')">Saldırı</button>
    <button class="specialAttack" v-if="gamerNumberOfLives!=0 " @click="attack('specialAttack')" >Özel Saldırı</button>
    <button class="firstAid" @click="attack('firstAid')" >İlk yardım</button>
    <button class="giveUp" v-if="gamerNumberOfLives!=0" @click="attack('giveUp')">Pes Et</button>
  </div>
  <div class="log">
    <h3 class="logsText">Logs</h3>
    <div class="result" v-for="(item, index) in logsGamer" :key="index">
    <div class="gamerResut">
      <h3>Canavarın canının azaltman ({{item}})</h3>
    </div>
    <div class="monsterResult">
      <h3>Canavarın saldırısı ({{logsMonster[index]}})</h3>
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
      monsterNumberOfLives:100,
      gamerNumberOfLives:100,
      logsGamer:[],
      logsMonster:[]
    }
  },
  props: {
    msg: String
  },
  methods:{
    attack:function(status){
      console.log(this.logsGamer,this.logsMonster)
      if(status=="attack" && this.monsterNumberOfLives>0 &&  this.gamerNumberOfLives>0 ){
      this.logsGamer.push(10);
      this.monsterNumberOfLives-=10;
      this.logsMonster.push(20);
      this.gamerNumberOfLives-=20;
      }
    
      if(this.gamerNumberOfLives!=100 && status=="firstAid"){
        if(this.gamerNumberOfLives+30>100){
        this.gamerNumberOfLives=100;
        }else{
          this.gamerNumberOfLives+=30;
        }
      }
      if(status=="specialAttack" && this.monsterNumberOfLives>0 && this.gamerNumberOfLives>0){
        if(this.monsterNumberOfLives-30<0){
          this.logsGamer.push(30);
          this.logsMonster.push(20);
          this.monsterNumberOfLives=0;
          this.monsterNumberOfLives-=30;
        }else{
          this.logsGamer.push(30);
          this.logsMonster.push(20);
          this.gamerNumberOfLives-=20;
          this.monsterNumberOfLives-=30;
        }
      }
      if(status=="giveUp"){
        this.logsGamer.push(0);
        this.logsMonster.push(0);
        this.gamerNumberOfLives=0;
        this.monsterNumberOfLives=100;
      }


    
  }
}}
</script>
<style>
.gamers{
  display: flex;
  justify-content: center;
  align-items: center;
}
.gamer{
  width: 22%;
  padding-right: 8rem;
}
.monster{
  width: 22%;
}
.gamerNumberOfLives{
  background-color: green;
}
.monsterNumberOfLives{
  width:100%;
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

