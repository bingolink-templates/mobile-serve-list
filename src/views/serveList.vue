<template>
  <div class="news">
    <!-- 服务号消息列表 -->
    <div class="serve-list">
      <div class="news-list-title flex">
        <div class="title-main flex">
          <bui-image src="/image/test.jpg" radius='10' width="40px" height="40px"></bui-image>
          <text class="c3">泊云客</text>
        </div>
        <text class="f26 c9" @click="serveMoreEvent">更多</text>
      </div>
      <div class="serve-list-content">
        <div class="content-item flex serve-item" v-for="(item,index) in serveList" :key='index'
          @click='serveListItemEvent(index)'>
          <text class="f30 c6 w550 lines1">个信需求接受or拒接,解密产品组和项目1111111111111111</text>
          <text class="f22 c6">03-04</text>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    data() {
      return {
        serveList: ['', '', '', '', '']
      }
    },
    methods: {
      // 服务号更多
      serveMoreEvent() {
        this.$alert('服务更多')
      },
      // 服务号列表
      serveListItemEvent() {
        this.$alert('服务号列表')
      }
    }
  }
</script>

<style lang="css" src="../css/common.css"></style>
<style>
  .news {
    flex: 1;
    background-color: #f2f2f2;
  }

  .title-main {
    width: 150px;
  }

  .content-item {
    padding: 20px;
    border-top: 1px solid #eee;
  }

  .news-list-title {
    padding: 0 20px;
    height: 86px;
  }

  .news-list {
    background-color: #fff;
    border-radius: 10px;
    margin-bottom: 20px;
  }

  .serve-list {
    background-color: #fff;
    border-radius: 10px;
  }

  .serve-item {
    height: 100px;
  }
</style>