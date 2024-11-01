<template>
  <div class="block">Click HERE {{ delay }}</div>
</template>

<script>
export default {
    props: ['delay']

}
</script>

<style>
.block{
    background-color: rgb(137, 238, 238);
    width: 400px;
    height: 300px;
    margin: 20px auto;
    padding-top: 30px;
    border-radius: 10px;
    box-shadow: 8px 8px 3px grey;
}
</style>