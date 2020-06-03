<template>
  <div>
    <Echart></Echart>
    <Liner></Liner>
    
    <div class='xpf'>{{msg}}</div>
    <List title='数据列表' :data='listData'>
      <template v-slot='slot'>
        <div>{{slot.scope.id}}</div>
        <div>{{slot.scope.name}}</div>
      </template>
    </List>

    <button @click="currentPage = 'Article'">文章管理</button>
    <button @click="currentPage = 'Category'">栏目管理</button>
    <button @click="currentPage = 'User'">用户管理</button>
    <keep-alive>
      <component :is="currentPage"></component>
    </keep-alive>
  </div>
</template>
<script>
// 导入组件
import List from './components/List.vue'
import Article from './pages/Article.vue'
import Category from './pages/Category.vue'
import User from './pages/User.vue'
import Liner from './components/Liner.vue'

// 导入echarts图表
import Echart from './components/Echart.vue'

export default {
  name: 'App',
  components:{
    List,
    Article,
    User,
    Category,
    Liner,
    Echart
  },
  data(){
    return {
      currentPage:'Article',
      msg:'hello vue-cli',
      listData:[{
        id:1,
        name:'军事'
      },{
        id:2,
        name:'爱情'
      },{
        id:3,
        name:'历史'
      }]
    }
  }
}
</script>
<style scoped>
  .xpf{
    background-color: red;
  }
</style>

