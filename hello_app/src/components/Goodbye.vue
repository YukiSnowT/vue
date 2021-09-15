<template>
  <div class="alert alert-danger">
    <h2 style="color:blue">{{ title }}</h2>
    <p>{{ message }}</p>
    <h5 class="text-light">{{ comment }}</h5>
  </div>
</template>

<script>
export default {
  name:"Goodbye",
  props:{
    title:String,
    message:String,
    comment:String,
  }
}

</script>