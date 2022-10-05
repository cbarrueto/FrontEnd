<template>
  <div id ="app" class="app">
    <div class="header">
      <h2><img src="../fotos/logoMedPies.png"></h2>
         <h4>CENTRO PODOLÓGICO<h6>PRODUCTOS Y TRATAMIENTOS PARA SUS PIES</h6></h4>
         
         <!-- Width="10px" heigth="10px" -->
         <!-- ../fotos/logo.jpg -->
      <nav>
        <button v-if="is_auth" v-on:click="loadHome">Inicio</button>
        <button v-if="is_authp" v-on:click="loadProductos">Productos</button>
        <button v-if="is_auth" v-on:click="loadAccount">Cuenta</button>
        <button v-if="is_auth" v-on:click="logOut">Cerrar sesión</button>
        <button v-if="!is_auth" v-on:click="loadLogIn">Iniciar sesión</button>
        <button v-if="!is_auth" v-on:click="loadSignUp">Registrarse</button>
      </nav>
    </div>

    <div class="main-component">
      <router-view  v-on:completedLogIn="completedLogIn"
                    v-on:completedSignUp = "completedSignUp"
                    v-on:logOut="logOut"
                    v-on:loadProductos="completeProductos"
                    
                    
                    >
      </router-view>
      <div class="footer">
      <h2>Grupo 3 - Misión TIC 2022</h2>

    </div>
    </div>


  </div>
</template>

<script>
export default {
  name: 'App',
  data: function(){
    return{
      is_auth: false,
      is_authp: true,
      
    }
  },
  methods:{
    verifyAuth: function(){
      this.is_auth = localStorage.getItem("isAuth") || false
      if(this.is_auth==false)
        this.$router.push({name:'logIn'})
      else
        this.$router.push({name:'home'})
    },

    loadLogIn: function(){
      this.$router.push({name:'logIn'})
    },
    loadSignUp: function(){
      this.$router.push({name:'signUp'})
    },
    loadHome:function(){
      this.$router.push({name:'home'})
    },
    loadAccount:function(){
      this.$router.push({name:'account'})
    },
    loadProductos:function(){
      this.$router.push({name:'Productos'})
    },

    completeProductos:function(data){

    },



    logOut:function(){
      localStorage.clear()
      alert("Sesión cerrada")
      this.verifyAuth()
    },
    completedLogIn: function(data){
      localStorage.setItem("username",data.username),
      localStorage.setItem("token_access",data.token_access),
      localStorage.setItem("token_refresh",data.token_refresh),
      localStorage.setItem("isAuth",true),
      alert("Autenticación exitosa")
      this.verifyAuth()
    },
    completedSignUp: function(data){
      alert("Registro exitoso")
      this.completedLogIn(data)
    },
  },
  created: function(){
    this.verifyAuth()
  }
}
</script>

<style>
body{
  margin: 0 0 0 0;
  }
.caja1{
  margin-left:35px;
  margin-bottom:20px;
} 
.header{
  margin: 0%;
  padding: 0;
  width: 100%;
  height: 10vh;
  min-height: 100px;
  background-color: #283747 ;
  color:#E5E7E9 ;
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.header h1 {
  width: 20%;
  text-align: left;
  margin: 30px;
  }
.header h2 {
  /* width: 10px; */
  /* height: 10px; */
  display: flex;
  /* text-indent: -999px; */
  height: 90px;
  width: 240px;
  margin: none;
  text-align: left;
  margin: 15px;
}
.header nav {
  height: 100%;
  width: auto;
  display: flex;
  justify-content: flex-end;
  align-items: center;
  font-size: 20px;
  margin: 15px;
}
  .header nav button{
  color: #E5E7E9;
  background: #283747;
  border: 1px solid #E5E7E9;
  border-radius: 5px;
  padding: 10px 20px;
}
.header nav button:hover{
  color: #283747;
  background: #E5E7E9;
  border: 1px solid #E5E7E9;
}
.main-component{
  height: 75vh;
  margin: 0%;
  padding: 0%;
  background: #FDFEFE;
}
.footer{
  margin:0;
  padding:0;
  width: 100%;
  height: 10vh;
  min-height: 100px;
  background-color: #283747;
  color: #E5E7E9;
  }
 .footer h2{
 width: 100%;
 height: 100%;

 display: flex;
 justify-content: center;
 align-items: center;
 }

</style>