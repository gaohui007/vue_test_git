<template>
  <div class="row">
      <div class="users" v-for="users in userList" :key="users.login">
          <a :href="users.html_url" target="_blank">
              <img :src="users.avatar_url" alt="" style="width:100px">
          </a>
          <p>{{users.login}}</p>
      </div>
      
  </div>
</template>

<script>
export default {
    name:"List",
    data(){
        return{
            userList:[]
        }
    },
    mounted(){
       this.$bus.$on('getUsers',(users)=>{
           this.userList = users
       })

    }
}

</script>

<style scoped>
.row{
    display: flex;
    flex-wrap:wrap;
    justify-content: space-around;
}
.users{
    flex: 1;
    background-color: pink;
    margin:20px;
 
}

</style>