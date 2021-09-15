<template>
  <div id="app">
    <mondai title="なぞなぞ" v-bind:message="que.qn"/>
    <div class="alert">
    <h3 ref="title" class="title" style="text-align:center;width:400px;margin:30px auto 0 auto">選択肢</h3>
    </div>
    <div id="sentakushi">
      <sentaku id="A" v-bind:select="ans.an.A" v-bind:answer='ans.an.T' number="A" />
      <sentaku id="B" v-bind:select="ans.an.B" v-bind:answer='ans.an.T' number="B" />
      <sentaku id="C" v-bind:select="ans.an.C" v-bind:answer='ans.an.T' number="C" />
      <sentaku id="D" v-bind:select="ans.an.D" v-bind:answer='ans.an.T' number="D" />
    </div>
    <button class="btn btn-info mt-2" style="display:block; text-align:center; margin:auto; width:100px" v-on:click="DoAction">更新</button>
  </div>
</template>

<script>
import mondai from './components/mondai.vue';
import sentaku from './components/sentaku.vue';

export default {
  name:"App",
  components:{
    mondai,
    sentaku,
  },
  data(){
    return {
      que:{
        qn:"根は植物。本は楽器。炭は回転。では盆は？",
        q1:"根は植物。本は楽器。炭は回転。では盆は？",
        q2:"木々は２。幹は６。柿は１０。では四季は？",
        q3:"白は「S」。黒は「K」。赤は「K」。では青は？",
        q4:"M M Z □ T T F F S S 　　□に入るのは？",
        q5:"島は青。石は緑。姉妹は黒。では今は？",
        q6:"梅にあって松にない。涙にあって涎にない。時にあって間にない。天気にあって気象にない。では次のうちあるのは？",
        q7:"過去にあって未来にない。雨にあって晴れにない。悲しみにあって喜びにない。幸せにあって不幸にない。では次のうちあるのは？",
        q8:"運にあって実力にない。汁にあって椀にない。脳にあって心にない。では次のうちあるのは？",
        
      },
      ans:{
        an:{A:"三国志", B:"太陽系", C:"化学式", D:"体組織", T:"D"},
        a1:{A:"三国志", B:"太陽系", C:"化学式", D:"体組織", T:"D"},
        a2:{A:"４", B:"７", C:"１１", D:"１６", T:"C"},
        a3:{A:"「A」", B:"「K」", C:"「S」", D:"「O」", T:"C"},
        a4:{A:"「Z」", B:"「O」", C:"「X」", D:"「S」", T:"B"},
        a5:{A:"赤", B:"黄", C:"白", D:"灰", T:"A"},
        a6:{A:"二月", B:"五月", C:"八月", D:"十一月", T:"B"},
        a7:{A:"リンゴ", B:"ミカン", C:"イチゴ", D:"レモン", T:"D"},
        a8:{A:"皿", B:"箸", C:"匙", D:"包丁", T:"A"},
      }
    }
  },
  mounted(){
    this.counter = 0
  },
  methods: {
    DoAction(){
      this.counter = Math.floor(Math.random()*(Object.keys(this.que).length-1))+1;
      this.que.qn=eval("this.que.q" + this.counter);
      this.ans.an.A=eval("this.ans.a" + this.counter + ".A");
      this.ans.an.B=eval("this.ans.a" + this.counter + ".B");
      this.ans.an.C=eval("this.ans.a" + this.counter + ".C");
      this.ans.an.D=eval("this.ans.a" + this.counter + ".D");
      this.ans.an.T=eval("this.ans.a" + this.counter + ".T");
      document.getElementsByClassName("title")[0].innerText="選択肢"
    }
  },
}

</script>
