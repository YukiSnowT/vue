<template>
  <div class="alert alert-info" style="text-align:center;width:600px;margin:10px auto">
    <h2 style="color:red;margin:0 0 20px 0">{{ title }}</h2>
    <h5>{{ message }}</h5>
  </div>
</template>

<script>
export default {
  name:"mondai",
  props:{
    title:String,
    message:String
  }
}
</script>