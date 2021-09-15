<template>
  <div class="alert alert-info" style="text-align:center;width:200px;height:200px;margin:0;" v-on:click="doAction">
    <h5 style="fontSize:8em;">{{ message }}</h5>
  </div>
</template>

<script>
export default {
  name:"masu",
  props:{
    type:String,
    message:String,
    counter:Number
  },
  methods: {
      doAction(){
          this.$emit("change",this.type)
      }
  },
}
</script>