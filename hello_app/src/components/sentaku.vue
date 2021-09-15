<template>

  <div class="alert alert-danger selecter" style="text-align:center;width:400px;margin:10px auto">
    <h4 class="select" v-on:click="doAction" style="cursor: pointer">{{ number }}:{{ select }}</h4>
  </div>
</template>

<script>
export default {
  name:"sentaku",
  props:{
    select:String,
    answer:Boolean,
    number:String,
  },
  methods:{
      doAction(){
          if(this.answer===this.number){
              document.getElementsByClassName("title")[0].innerText="正解"
            // this.$refs.title.innerHTML="正解"
          }else{
              document.getElementsByClassName("title")[0].innerText="不正解"
            //   this.$refs.title.innerHTML="不正解"
          }
      },
  }
}
</script>