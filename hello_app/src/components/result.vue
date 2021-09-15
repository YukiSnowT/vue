<template>
  <div class="alert alert-info" style="text-align:center;width:600px;margin:10px 0">
    <h2>{{ message }}</h2>
  </div>
</template>

<script>
export default {
  name:"result",
  props:{
    message:String
  }
}
</script>