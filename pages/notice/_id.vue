<template>
  <div class="container">
    <el-container direction="vertical" class="detail-container">
      <el-row type="flex" justify="center" >
        <el-col>
          <div class="detail-blog-box">
            <h2>{{say.title}}</h2>
            <el-row class="detail-inscribe" type="flex" align="bottom" justify="start">
              <el-col :span="10">时间：{{say.gmtCreate}}</el-col>
            </el-row>

            <article class="detail-blog-article" v-html="say.content"></article>
          </div>
        </el-col>
      </el-row>

    </el-container>
  </div>
</template>

<script>

    export default {
      data() {
        return {
          id: '',
          say: {}
        }
      }

    }
</script>

<style scoped>
  .detail-container{
    width: 850px;
    background: #fff;
    -webkit-border-radius: 8px;
    -moz-border-radius: 8px;
    border-radius: 8px;
  }
  .detail-blog-box{
    line-height: 30px;
    padding: 20px;
    border-radius: 8px;
  }
  .detail-blog-box h2{
    text-align: center;
    margin-bottom: 10px;
  }
  .detail-blog-article{
    color: #696969;
    text-indent: 2em;
  }
  .detail-inscribe{
    font-size: 13px;
    color: #8c8c8c;
  }
  .blog-edit{
    text-align: right;
  }
  .blog-edit a{
    width: 50px;
    height: 30px;
    line-height: 30px;
    display:inline-block;
    margin-left: 10px;
    text-align: center;
    cursor: pointer;
  }
  .blog-edit a:first-child{
    color: blue;
  }
  .blog-edit a:last-child{
    color: red;
  }
  .el-col-category ul li{
    list-style: none;
    padding: 0;
    margin-right: 10px;
    display: inline-block;
  }
</style>
