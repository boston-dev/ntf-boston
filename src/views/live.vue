<template>
  <div class="live-page">
    <AppTopBar
      :titleClass="['app-top-black-title']"
      topBarTitle="Live"
      :styleObj="{
        backgroundColor: '#000',
        color: 'red',
      }"
    ></AppTopBar>
    <div class="list-box">
      <div class="list" v-for="i in 10" :key="i">
        <div class="img-box">
          <img src="" alt="" />
        </div>
        <div class="name app-multi-ellipsis--l2">
          2024 Asia Regionals - Playoffs RERUN: Lemon vs. Nanami - ESL SC2
          Masters Spring
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "LiveView",
};
</script>
<style scoped lang="less">
.live-page {
  ::v-deep {
    .app-top-black-title {
      color: #fff !important;
    }
  }
  .list-box {
    margin-top: 14px;
    .list {
      margin: 0 auto;
      margin-bottom: 20px;
      width: 343px;
      .img-box {
        width: 343px;
        height: 185.4px;
        border-radius: 10px;
        background: #fff;
        overflow: hidden;
        img {
          width: 343px;
          height: 185.4px;
        }
      }
      .name {
        color: #fff;
        margin-top: 11px;
        font-size: 12px;
      }
    }
  }
}
</style>
