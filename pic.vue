<template>
    <div id="wrapper">
        <div id="pic-wrapper">
            <ul id="ul-wrapper" ref="ulWrapper">
                <li class="picContent" v-for="(item,index) in list" >
                    <a v-bind:href="item.picUrl">
                        <img  alt="评价图片" v-bind:src="item.picUrlSmall">
                    </a>
                </li>
            </ul>
            <div class="pre goTo" @click="goToPre" v-show="!isFrist"><img src="left_rocket_white.png" width="20px" height="20px"></div>
            <div class="next goTo" @click="goToNext" v-show="!isLast"><img src="right_rocket_white.png" width="20px" height="20px"></div>
        </div>
        <!--//赞和回应-->
        <div class="response-wrapper">
            <span class="response">赞({{approveCount}})</span>
            <span class="response">回应({{replyCount}})</span>
        </div>
    </div>
</template>

<script type="text/ecmascript-6">

  export default {
    props:{

    },
      data: {
          currentIndex:1,
          list:[
              {
                  picId: 0,
                  picUrlSmall:"https://timgsa.baidu.com/timg?image=&quality=80&size=b9999_10000&sec=1525865680450&di=1e3dfe0f713330d6fcc3492e5b3de604&imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2F55e736d12f2eb938ef9a4ae1df628535e5dd6f29.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/NW_mCa9a3DwvhJwuOcFDDsEnfwhlzgA_4arKR4VV0hsVKCkHVKn3uRGGPguC_UDNTYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/G0ZRfz_rXQ38TbTWKsuRftuBXxH4eBpi2uRJr_yYnjwp9jCvUAVqkU2RgnLDsV24TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"https://timgsa.baidu.com/timg?image=&quality=80&size=b9999_10000&sec=1525865680450&di=1e3dfe0f713330d6fcc3492e5b3de604&imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2F55e736d12f2eb938ef9a4ae1df628535e5dd6f29.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"https://timgsa.baidu.com/timg?image=&quality=80&size=b9999_10000&sec=1525865680450&di=1e3dfe0f713330d6fcc3492e5b3de604&imgtype=0&src=http%3A%2F%2Fimgsrc.baidu.com%2Fimgad%2Fpic%2Fitem%2F55e736d12f2eb938ef9a4ae1df628535e5dd6f29.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },
              {
                  picId: 0,
                  picUrlSmall:"http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  picUrl: "http://qcloud.dpfile.com/pc/9vQetqapeVbe7VfeDwmEWjnv8nDr1H_spa1kvdv9XxgNVOy_o_TfQX-dnd9fN0d0TYGVDmosZWTLal1WbWRW3A.jpg",
                  spuName: "小肥羊",
                  qualityType: 0,
                  qualityScore: 0.05
              },

          ],
          len:0,
          approveCount:0,
          replyCount:0,
          isFrist:true,
          isLast:false,
      },
      watch:{
          //是否为首尾页
          currentIndex(){
              //是第一页
              if(this.currentIndex === 1){
                  this.isFrist = true;
                  if(this.currentIndex>(this.len)/7) {
                      this.isLast = true;
                  }else {
                      this.isLast=false;
                  }
              }else{
                  this.isFrist = false;
                  if(this.currentIndex>(this.len)/7){
                      this.isLast = true;
                  }else{
                      this.isLast = false;
                  }
              }
          }
      },
      mounted(){
          //         设置ul的宽度
          this.list.forEach((item,index)=>{
              this.len++
          });
          this.$refs.ulWrapper.style.width =`${(this.len+1)*96+(this.len)*6}px`;
          //如果总的图片数小于8
          if(this.len<8){
              this.isLast = true
          }
      },
      methods:{
          goToPre(){
              if(this.currentIndex>1){
                  this.currentIndex--;
                  this.changePos(1);
              }
          },
          goToNext(){
              if(this.currentIndex<(this.len/7)){
                  this.currentIndex++;
                  this.changePos(1);
              }
          },
          changePos(offset){
              this.$refs.ulWrapper.style.left = `${offset*(1-this.currentIndex)*762}px`;
          }
      }

  }
</script>

<style scoped>
    #wrapper{
        position: relative;
    }
    #pic-wrapper{
        width: 762px;
        height:170px;
        overflow: hidden;
        position: relative;
    }
    #ul-wrapper{
        /*取消浏览器自带padding*/
        padding:0;
        position: absolute;
        left:0;
        z-index:1;
    }
    .picContent{
        width:96px;
        height:170px;
        display: inline-block;
        margin-right: 6px;
        vertical-align: top;
    }
    .picContent img{
        width:96px;
        height: 96px;
    }
    .pre{
        left:0;
    }
    .next {
        right: 0;
    }
    .goTo{
        z-index:2;
        top:23%;
        width: 20px;
        height: 40px;
        color: white;
        padding-top: 20px;
        vertical-align: middle;
        background-color: black;
        opacity: 0.7;
        position: absolute;
        cursor: pointer;
    }
    .response-wrapper{
        margin-left: 300px;
    }
    .response{
        color: lightgrey;
        padding-right:20px;
        cursor: pointer;
    }

</style>
