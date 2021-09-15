<template>
  <div id="app">
    <div id="masuall" style="display:flex;flex-wrap:wrap;width:600px;height:600px;">
      <div v-for="item in title" v-bind:key="item.name">
        <masu v-bind:type="item.name" v-bind:message="item.type" v-bind:counter="this.counter" v-on:change="Change"/>
      </div>
    </div>
    <result v-bind:message="this.res"/>
  </div>
</template>

<script>
import masu from './components/masu.vue';
import Result from './components/result.vue';

export default {
  name:"App",
  components:{
    masu,
    Result,
  },
  data(){
    return {
      title:[
        {name:"A", type:"",id:"0"},
        {name:"B", type:"",id:"1"},
        {name:"C", type:"",id:"2"},
        {name:"D", type:"",id:"3"},
        {name:"E", type:"",id:"4"},
        {name:"F", type:"",id:"5"},
        {name:"G", type:"",id:"6"},
        {name:"H", type:"",id:"7"},
        {name:"I", type:"",id:"8"},
        ],
      counter:0,
      check:[0,0,0,0,0,0,0,0,0],
      resultGet:false,
      res:null
    }
  },
  methods: {
    Change(int){
      if(!this.resultGet){
      const target = this.title.find((n)=>n.name === int);
      if(target.type===""){
        if(this.counter%2===0){
          target.type="〇";
          this.check[target.id]=1;
        }else{
          target.type="✖"
          this.check[target.id]=2;
        }
        this.counter++;
        for(let i=0;i<3;i++){
          if(this.check[i*3]===this.check[i*3+1]&&this.check[i*3]===this.check[i*3+2]&&this.check[i*3]!==0){
            this.res = target.type + "の勝ち"
            this.resultGet=true;
          }
          if(this.check[i]===this.check[i+3]&&this.check[i]===this.check[i+6]&&this.check[i]!==0){
            this.res = target.type + "の勝ち"
            this.resultGet=true;
          }
        }
        if(this.check[0]===this.check[4]&&this.check[0]===this.check[8]&&this.check[0]!==0){
            this.res = target.type + "の勝ち"
            this.resultGet=true;
        }
        if(this.check[2]===this.check[4]&&this.check[2]===this.check[6]&&this.check[2]!==0){
            this.res = target.type + "の勝ち"
            this.resultGet=true;
        }
      }
      }
    }
  },
}

</script>
