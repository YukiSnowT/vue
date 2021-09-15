<template>
  <div class="alert alert-info">
    <h2>{{ title }}</h2>
    <p ref="msg">{{ message }}</p>
      <button class="btn btn-info mt-2" v-on:click="DoAction">Click</button>
  </div>
</template>

<script>
export default {
  name:"HelloWorld",

  data(){
    return {
      title:"HelloWorld",
      message: "This is sample message.",
    }
  },
  mounted() {
    this.counter=0
  },
  methods: {
    DoAction(){
      this.counter++
      this.$refs.msg.innerHTML += "<h6>counted:" + this.counter + "</h6>"
    }
  }
}
</script>