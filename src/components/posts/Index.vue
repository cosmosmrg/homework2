<template>
  <div class="posts">
    <!-- <el-card class="box-card"> -->

      <div v-for="post in posts" :key="post.id" class="text item">
        <router-link :to="{ name: 'Posts.show', params: {id: post.id } }">
          <iccs340-post :post='post'></iccs340-post>
        </router-link>
      </div>
    <!-- </el-card> -->
    <!-- <md-list class="custom-list md-triple-line" v-for="post,key in posts" :key="post.id">
      <router-link :to="{ name: 'Posts.show', params: {id: post.id } }">
        <iccs340-post :post='post'></iccs340-post>
      </router-link>
    </md-list> -->
  </div>
</template>

<script>
import PostsApi from '../../api/posts.js'

export default {
  name: 'posts',
  data () {
    return {
      posts: null,
      error: null
    }
  },
  components: {
    Iccs340Post: require('./Post')
  },
  beforeRouteEnter (to, from, _next) {
    PostsApi.getPosts(_posts => {
      _next(vm => {
        vm.posts = _posts
      })
    })
  },
  watch: {
    $route () {
      PostsApi.getPosts(_posts => {
        this.posts = _posts
      })
    }
  }
}
</script>

<style scoped>
  .posts {
    padding: 0 10px;
  }
  .box-card {
    width: 100%;
    margin-left: 0%;
    margin-top: 5%;
  }
</style>
