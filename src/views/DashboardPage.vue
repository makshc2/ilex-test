<template>
  <div class="dashboard-wrapper flex full-width scroll-y">
    <NavigationComponent @filter-post="filterPosts"/>
    <div class="wrapper-content flex column justify-between">
      <SearchComponent />
      <span class="today-title q-ml-md">Today</span>
      <div class="posts-wrapper flex row">
        <AllPostsComponents
          v-for="(post, index) in allPosts"
          :key="index"
          :title="post.title"
          :description="post.body"
          :id="post.id"
          @open-post="openPost"
        />
      </div>
    </div>
  </div>
</template>

<script>
import NavigationComponent from "@/components/navigationComponents/NavigationComponent"
import SearchComponent from "@/components/dashboardComponents/SearchComponent"
import AllPostsComponents from "@/components/dashboardComponents/AllPostsComponents"
import api_urls from '../app-constans/api-urls.js'

export default {
name: "DashboardPage",
  components:{
    NavigationComponent,
    SearchComponent,
    AllPostsComponents
  },
  data(){
    return{
      allPosts:[]
    }
  },
  methods:{
    getAllPosts () {
      this.axios.get(api_urls.all_posts)
        .then(({data}) => {
          this.allPosts = data
        })
    },
    filterPosts (id) {
      this.allPosts = this.allPosts.filter(item => item.userId === id)
    },
    openPost (id) {
      console.log(id)
    }
  },
  mounted() {
    this.getAllPosts()
  }
}
</script>

<style scoped>

</style>
