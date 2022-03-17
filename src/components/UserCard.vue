<template>
   <div class="card">
       <div class="card-body">
           <h1>{{fullName}} </h1>
           <small>@{{user.username}} <span v-if="user.isAdmin" class="admin-badge">Admin</span></small>
           <p>Followers: {{followers}}  <span class="text-right"> <button @click="followUser">Follow</button> </span></p>
       </div>
    </div>
</template>

<script>
export default {
  name: 'useCard',
  data(){
    return {
      followers: 0,
      user: {
        id: 1,
        username: "MohsinMalik",
        firstname: "Mohsin",
        lastname: "Nawaz",
        email:"malikmuhsin70@gmail.com",
        isAdmin: true

      }
    }
  },
  watch:{
    followers(newFollowerCount , oldFollowerCount){

      if(newFollowerCount > oldFollowerCount){
        console.log(this.user.username + " gained a follower")
      }

    }
  },
  computed:{
    fullName(){
      return `${this.user.firstname} ${this.user.lastname}`;
    }
  },
  methods:{
    followUser(){
      this.followers++;
    }
  }
}
</script>

<style>
 .text-right{
     float: right;   
    }
.card{
    border-radius:9px;
    background: #fff;
    border: 1px solid red;
    flex-wrap: wrap;
    width:265px;
   
}
.card-body{
        padding:15px;
}
.admin-badge{
    background: purple;
    color:#fff;
    padding:5px 10px;
    float:right;
    border-radius:9px;
}
</style>