<template>
    <div id="pic-detail-wrapper" v-show="isShowPicDetail">
        <ul id="pic-detail">
            <li v-for="item in list">{{item.spuName}}:{{item.score}}</li>
        </ul>
        <div id="picMessage-wrapper">
            <div class="picMessage">{{goodProbability}}</div>
            <a v-bind:href="picUrlBig"><img v-bind:src="picUrlBig"></a>
        </div>
    </div>
</template>

<script type="text/ecmascript-6">

  export default {
    props:{

    },
      data: {
          picId:0,
          picUrlBig:"http://qcloud.dpfile.com/pc/ruXQxOQgqlChSPnembVMqC4DuXyHGXPyFy8dQBqkU7wRHTLVxYhiy25HOKPLfghQ.jpg",
          list:[{
              spuName:"小肥羊",
              score:0
          }],
          goodProbability:0.2,
          isShowPicDetail:false,
      },

  }
</script>

<style scoped>
    .picMessage{
        text-align: center;
    }
    #picMessage-wrapper,#pic-detail{
        display: inline-block;
        list-style-type: none;
        vertical-align: top;
    }
</style>
