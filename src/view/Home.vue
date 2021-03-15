<template>

  <div class="home">
    <div class="title">
      hi ,<span class="user">{{user}}</span> ! 
      <br>
      welcome to UNIQUE love
    </div>

  </div>

</template>

<script>
import axios from 'axios'

export default {
  name:'Home',
  data(){
    return{
      user:'anl'
    }
  },
  created(){
    axios.get("https://interface.sina.cn/news/wap/fymap2020_data.d.json")
            .then(response=>{
                console.log("http请求成功")
                console.log(response); // http响应对象
                console.log(response.data); // 返回的数据
            })
            .catch(error=>{
                // 请求失败或者then里面代码出现错误时
                console.log("http请求失败或者then里面代码报错");
                console.log(error);
                console.log(error.response.data); // 如果希望获取来自服务器的错误信息
            })
  }
}
</script>

<style>
  .home{
    height: 100vh;
    width: 100vw;
    position: relative;
  }
  .title{
    font-size: 34px;
    font-weight: 600;
    color: rgb(218, 139, 152);
    z-index: 2;
  }

  .user{
    color: rgb(233, 140, 228);
  }
  
</style>