<template>
  <div class="alert alert-info">
    <h2 style="color:red">{{ title }}</h2>
    <p>{{ message }}</p>
    <h5 class="text-primary">{{ comment }}</h5>
  </div>
</template>

<script>
export default {
  name:"HelloWorld",
  props:{
    title:String,
    message:String,
    comment:String,
  }
}
</script>