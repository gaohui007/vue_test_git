<template>
  <div>
      <h2>搜索GITHUB</h2>
      <div>
          <input type=" test" placeholder="输入关键字" v-model="keyWords">
          <button @click="getKeyWords">点我搜索</button>
      </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
name:"Search",
data(){
    return {
        keyWords:''
    }
},
methods:{
    getKeyWords(){
        axios.get(`https://api.github.com/search/users?q=${this.keyWords}`).then(
        response => {console.log('成功',response.data)
        this.$bus.$emit('getUsers',response.data.items)
        },
            erro => {console.log('失败')}
        )
    }
}
}
</script>

<style>

</style>