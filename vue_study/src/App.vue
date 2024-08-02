<script >

export default{
  data(){
    return{
      num:0,
      uname:'张三',
      msg:'测试消息',
      htmlData:'<h2> html 数据<h2>',
      id:'id1',
      imgUrl1:'https://bossaudioandcomic-1252317822.image.myqcloud.com/activity/document/1572193a14e307f2e79d6bc69d1ff471.jpg',
      attributeName:'id',
      mouseEvent:'click',
      mouseEventButtonText:'点击事件'
    }
  },
  methods:{
    changeMsg(){
      this.msg = "测试消息2"
    },
    chageImgUrl(){
      this.imgUrl1 = 'https://bossaudioandcomic-1252317822.image.myqcloud.com/activity/document/b99e3389c7a703aa99953c6cb5056004.jpg'
    },
    changeColor(){
      if(this.id == 'id1'){
        this.id = 'id2'
      }
      else{
        this.id = 'id1'
      }
    },
    changeMouseEvent(){
      this.mouseEvent ='mouseover'
      this.mouseEventButtonText = '滑动事件'

    }
  }
}
</script>

<template>
  <div class="body">

    <p>{{ num }}</p>
    <p>{{ uname }}</p>
    <p>{{ msg }}</p>
    
    <p v-once> {{ msg }}</p>
    <button @click="changeMsg"> 更改测试消息 </button>
    <p v-html="htmlData"> </p>
    <img v-bind:src="imgUrl1" alt="as">

    <button @click="chageImgUrl"> 改变图片Url </button>
    <p :id="id">dsa</p>
    <button v-on:click="changeColor"> 改变颜色 </button>

    <!-- 动态属性 -->
    <p v-bind:[attributeName]="id"> 动态属性 </p>
    <button v-on:click="attributeName = 'class'"> 改变属性 </button>
    <!-- 动态事件 -->
    <button v-on:[mouseEvent] = "attributeName = 'class'"> {{ mouseEventButtonText }}</button>
    <button @click="changeMouseEvent"> 改变事件 </button>
    test2
  </div>
</template>

<style>
.body{
  padding-top: 100px;
  margin-top: auto;
}
#id1{
  color: red;
}
#id2{
  color:blue;
}
.id1{
  color: aquamarine;
}
</style>