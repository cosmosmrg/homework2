<template>
  <div class="new-post">
    <el-card class="box-card">
      <span>Adding a new comment</span>
      <el-input  type="textarea" v-model="comment.content" placeholder=""></el-input>
      <el-button style="margin-left:40%;margin-top:2%"type="primary" @click.native="createComment">Save</el-button>
    </el-card>
  </div>
</template>

<script>
import CommentsApi from '../../api/comments.js'
import router from '../../router'

export default {
  name: 'new-comment',
  data () {
    return {
      comment: {
        content: ''
      }
    }
  },
  props: {
    post: {
      type: Object,
      required: false,
      default: {}
    }
  },
  methods: {
    createComment () {
      var postId = this.post.id
      var content = this.comment.content
      this.comment.content = ''
      CommentsApi.createComment(postId, content,
        function (_comment) {
          // console.log(_comment)
          router.push({ name: 'Posts.show', params: { post_id: postId }, query: { t: new Date() } })
        }
      )
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
