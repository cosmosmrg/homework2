<template>
  <div class="new-post">
    <el-card class="box-card">
      <div slot="header" class="clearfix">
        <i class="el-icon-document"></i>
        <span style="line-height: 36px; margin-left: 10px"> New Post</span>
      </div>
      <div class="text" >
        <el-form label-width="120px">
          <el-form-item label="Name">
            <el-input v-model="post.name" placeholder=""></el-input>
          </el-form-item>
          <el-form-item label="Content">
            <el-input type="textarea" v-model="post.content" placeholder=""></el-input>
          </el-form-item>
          <el-button style="margin-left:40%"type="primary" @click.native="createPost">Save</el-button>
        </el-form>
      </div>

    </el-card>
  </div>
</template>

<script>
import PostsApi from '../../api/posts.js'
import router from '../../router'

export default {
  name: 'new-post',
  data () {
    return {
      post: {
        name: '',
        content: ''
      }
    }
  },
  methods: {
    createPost () {
      PostsApi.createPost(this.post,
        function (_post) {
          router.push({ name: 'Posts.index' })
        }
      )
    }
  }
}
</script>

<style scoped>

</style>
