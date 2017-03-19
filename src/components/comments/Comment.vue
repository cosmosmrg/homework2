<template>
  <div class="comment">
    <el-card class="box-card">
      {{ comment.user.email }} : {{ comment.content }}
    </el-card>

  </div>
</template>

<script>

export default {
  name: 'comment',
  props: {
    comment: {
      type: Object,
      required: false,
      default: {}
    }
  }
}
</script>

<style scoped>
  .box-card {
    width: 480px;
    margin-left: 10%;
    margin-top: 0.5%;
  }
</style>
