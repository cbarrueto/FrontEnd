<template>
  <div class="information">
      <h1>Información de la cuenta:</h1>
      <h2>Nombre: <span>{{name}}</span></h2>
      <h2>Saldo: <span>{{balance}}</span> Pesos</h2>
      <h2>Correo electrónico <span>{{email}}</span> </h2>
  </div>
</template>

<script>
import axios from 'axios'
import jwt_decode from 'jwt-decode'

export default {
  name: "Account",
  data: function(){
      return{
          name:"",
          email:"",
          balance:0
      }
  },
  methods:{
      verifyToken: function() {
          return axios.post(
              "https://primero01.herokuapp.com/refresh/",
              {refresh:localStorage.getItem("token_refresh")},
              {headers:{}}
          )
          .then((result)=>{
              localStorage.setItem("token_access", result.data.access)
          })
          .catch(()=>{git 
              this.$emit('logOut')
          })
      },
      getData: async function(){
          if (localStorage.getItem("token_access")===null || localStorage.getItem("token_refresh")===null){
              this.$emit('logOut')   
              return;
          }
          await this.verifyToken()
          let token = localStorage.getItem("token_access")
          let userId = jwt_decode(token).user_id.toString()

          axios.get(`https://primero01.herokuapp.com/user/${userId}/`,
          {headers:{'Authorization': `Bearer ${token}`}})

          .then((result)=>{
              this.name = result.data.name
              this.email = result.data.email
              this.balance = result.data.account.balance
          })
          .catch(()=>{
              this.$emit('logOut')
          })

      }
  },
  created: async function(){
      this.getData()
  }
}
</script>

<style>
.information{
  margin: 0;
  padding: 0%;
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}
.information h1{
  font-size: 60px;
  color: #0f1316;
}
.information h2{
  font-size: 40px;
  color: #283747;
}
.information span{
  color: crimson;
  font-weight: bold;
}

</style>