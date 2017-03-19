<template>
  <div class="post">
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <i class="el-icon-document"></i>
        <span style="line-height: 36px; margin-left: 10px"> {{ post.name }}</span>
      </div>
      <div class="text" >
        {{ post.content }}
      </div>

    </el-card>

    <!-- <md-list-item>
      <md-avatar>
        <md-icon>announcement</md-icon>
      </md-avatar>

      <div class="md-list-text-container">
        <span>{{ post.name }}</span>
        <p>{{ post.content }}</p>
      </div>

      <md-button class="md-icon-button md-list-action">
        <md-icon class="md-primary">code</md-icon>
      </md-button>

      <md-divider class="md-inset"></md-divider>
    </md-list-item> -->
  </div>
</template>

<script>

export default {
  name: 'post',
  props: {
    post: {
      type: Object,
      required: false,
      default: {}
    }
  }
}
</script>

<style scoped>
  .text {
    font-size: 14px;
    padding-left: 30px;
  }
  .clearfix:before,
  .clearfix:after {
      display: table;
      content: "";
  }
  .clearfix:after {
      clear: both
  }
  .box-card {
    width: 100%;
    margin-left: 0%;
    margin-top: 0%;
  }
</style>
