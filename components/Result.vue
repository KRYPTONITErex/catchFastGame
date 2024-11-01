<template>

    <p id="P">RESULT IS {{ score }} ms</p>

    <div v-if="score<250">
        <p>U are too FAST</p>
    </div>
    <div v-else-if="score>250 && score<500">
        <p>U are Normal</p>
    </div>
    <div v-else>
        <p>U are TOOO SLOWWWW ! try again</p>
    </div>
  
</template>

<script>
export default {
    props: ['score']

}
</script>

<style>
#P{
    font-weight:600;
    color: rgb(181, 131, 4);
    border: .5px solid black;
    padding: 5px;
    width: 200px;
    margin: auto;
    margin-bottom: 20px;
    background-color: rgb(252, 245, 211);
    box-shadow: burlywood 2px 2px;
    border-radius: 10px;
}

</style>