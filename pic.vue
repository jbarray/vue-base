<template>
    <div>
        <div id="pic-wrapper">
            <ul>
                <li class="picContent" v-for="(index , item) in picInfoList" :key="index" v-show="currentIndex-1<index && index<currentIndex+7">
                    <img :src="item.picUrl" alt="评价图片">
                    <div>{{item.supName}}</div>
                    <div>{{type}}:{{item.qualityScore}}</div>
                </li>
            </ul>
            <div class="pre"><</div>
            <div class="next">></div>
        </div>
        <!--//赞和回应-->
        <div></div>
    </div>
</template>

<script type="text/ecmascript-6">

  export default {
    props:{
        picInfoList:{
          default:0,
          type:Array,
      }
    },
      data(){
        return {
            currentIndex:0
        }
      },
      computed:{
          type(){
              this.picInfoList.forEach((index)=>{
                  if(!this.picInfoList[index].qualityType){
                      this.type[index]=' '
                  }
                  if(this.picInfoList[index].qualityType===0){
                      this.type[index]='好'
                  }else{
                      this.type[index]='差'
                  }
              })
          }
      }

  }
</script>

<style scoped>
    #pic-wrapper{
        width: 714px;
        background-color: red;
    }
    .picContent{
        display: inline-block;
        margin-right: 6px;
    }
    .picContent>img{
        width:96px;
        height: 96px;
    }

</style>
