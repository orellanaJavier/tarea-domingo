<template>
  <div class="hello">
    <h1 v-formato="'mayuscula'">{{ msg }}</h1>
    
 <p>yo soy mi propio gefe</p>
    
    
  
    <h1>Lista de peliculas</h1>
    <div id='main'>
      <ul>
       <li v-for="(item,index) in lista" :key="index" > 
         {{ item.nombre }} - {{ item.anio }} 
       </li>
      </ul>
    </div>

    <div v-html="nombres"></div>

  </div>

</template>

<script>
export default {
  name: 'HelloWorld',
  props: {

    msg: String

  },
  data(){
    return {
       lista:[
         {nombre: 'dumbo',anio:2014},
         {nombre: 'titanic',anio:1990},
         {nombre: 'upgrade',anio:2016},
         {nombre: 'argo',anio:2012},
         {nombre: 'sin city',anio:2010}
         ],
         nombres: `
          <span> <h2><em>Integrantes:</em></h2></span> <text-align: center> 
          <span> <h2><em>Jacobo Eduardo Portillo</em></h2></span>
          <span> <h2><em>Francisco Javier Orellana</em></h2></span>
         `
    }
  },
  directives:{ 
    formato:function(el,binding){
      if(binding.value == "minuscula"){
        el.style.textTransform ='lowerCase'
      }
       else if(binding.value == "mayuscula"){
        el.style.textTransform ='upperCase'
      }
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  padding: 0;
}
li {
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
