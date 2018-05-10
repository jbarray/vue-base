<template>
    <div id="pic-detail-wrapper">
        <div class="picMessage"></div>
        <ul id="pic-detail">
            <li v-for="item in list">{{item.spuName}}:{{item.score}}</li>
        </ul>
        <a v-bind:href="picUrlBig">
            <img v-bind:src="picUrlBig">
        </a>
    </div>
</template>

<script type="text/ecmascript-6">

  export default {
    props:{

    },
      data: {
          picId:0,
          picUrlBig:"http://qcloud.dpfile.com/pc/NW_mCa9a3DwvhJwuOcFDDsEnfwhlzgA_4arKR4VV0hsVKCkHVKn3uRGGPguC_UDNTYGVDmosZWTLal1WbWRW3A.jpg",
          list:[{
              spuName:"小肥羊",
              score:0
          }],
          goodProbability:0.2
      },

  }
</script>

<style scoped>
    #pic-detail{
        display: inline-block;
        list-style-type: none;
    }
</style>
