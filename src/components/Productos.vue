<template>

<table class="a"  >

<tr>
    <td>
        <img src="https://medicpies.com/wp-content/uploads/2019/12/YA.jpg" alt="Nature" class="img">
    </td>
    <td>
        <img src="https://plustatic.com/1952/conversions/tipos-pies-default.jpg" alt="Nature" class="img">
    </td>
    <td>
        <img src="http://image.ibb.co/fU16Pk/pedicure_infantil_todo_para_sus_pies_pie_plano.jpg" alt="Nature" class="img">  
    </td>
</tr>
<tr>
    <td  class= "f" >
        <h2>PEDICURE MEDICINAL</h2>
        <p>El pedicure medicinal es un procedimiento en el cual se realiza un correcto corte de uñas</p>
    </td>
    <td>
        <h2>ONICOMICOSIS</h2>
        <p > Es una infección por distintos tipos de hongos sobre las uñas, generando crónicamente  deformidad, engrosamiento, cambio de color y mal aspecto de la uña</p>
    </td>
    <td>
        <h2>PEDICURE MEDICINAL PARA NIÑOS</h2>
    </td>
    
</tr>
<tr>
    <td>
        <img src="https://medicpies.com/wp-content/uploads/2019/12/YA.jpg" alt="Nature" class="img">
    </td>
    <td>
        <img src="https://plustatic.com/1952/conversions/tipos-pies-default.jpg" alt="Nature" class="img">
    </td>
    <td>
        <img src="http://image.ibb.co/fU16Pk/pedicure_infantil_todo_para_sus_pies_pie_plano.jpg" alt="Nature" class="img">  
    </td>
</tr>
<tr>
    <td  class= "f" >
        <h2>PEDICURE MEDICINAL</h2>
        <p>El pedicure medicinal es un procedimiento en el cual se realiza un correcto corte de uñas</p>
    </td>
    <td>
        <h2>ONICOMICOSIS</h2>
        <p > Es una infección por distintos tipos de hongos sobre las uñas, generando crónicamente  deformidad, engrosamiento, cambio de color y mal aspecto de la uña</p>
    </td>
    <td>
        <h2>PEDICURE MEDICINAL PARA NIÑOS</h2>
    </td>
    
</tr>

</table>

</template>
  
<script>
export default {
    name:'Home',
    data: function(){
        return{
            username: localStorage.getItem("username")
        }
    }
}
  </script>
  
  <style>
.responsive {
  width: 100%;
  height: auto;
}
th, td {
   width: 25%;
   text-align: center;
   vertical-align: top;
   border: 1px solid #000;
   border-collapse: collapse;
   padding: 0.3em;
   caption-side: bottom;
}
.f{
    height : 10px;
    width:250px;
}

.greetings{
    margin: 0;
    padding: 0%;
    height: 100%;
    width: 100%;
    display: flex;
    justify-content: center;
    align-items: center;
}
.img {
    height: 250px;
    width: 250px;
}
.responsive {
  width:  400px;
  max-width: 400px;
  height: auto;
}
.greetings h1{
  font-size: 50px;
  color: #283747;
}
.greetings span{
  color: crimson;
  font-weight: bold;
}
.a{
  table-layout: auto;
  border: red 5px solid;
  margin: 15px;
  padding: 15px;  
  width: 1500px;  
}
</style>
  