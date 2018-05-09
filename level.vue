<template>
    <ul class="level-wrapper">
        <li v-bind:class="[level>0?'effectiveLevel':'unEffectiveLevel']">1</li><li v-bind:class="[level>1?'effectiveLevel':'unEffectiveLevel']">2</li><li v-bind:class="[level>2?'effectiveLevel':'unEffectiveLevel']">3</li>
    </ul>
</template>

<script type="text/ecmascript-6">

  export default {
    props:{
      level:{
          default:0,
          type:Number
      }
    }
  }
</script>

<style scoped>
    /*设置li样式*/
    .level-wrapper li{
        display: inline-block;
        padding: 0 5px;
        border: 1px solid gainsboro;
        margin-right: 1px;
    }
    /*有效评分样式*/
    .effectiveLevel{
        background-color: #EE7A23;
        color: white;
    }
    /*无效评分样式*/
    .unEffectiveLevel{
        background-color: ghostwhite;
        color: black;
    }
</style>
