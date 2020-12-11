<template>
  <div class="container">
    <h3>Alumnos del Diplomado</h3>
	<hr>
  <form @submit.prevent="agregar">
		<label>Nombre:</label>
			<input v-model="nombre" type="text" name="nombre" id="minombre" placeholder="Escribe tu nombre...">			

		<label>Apellido:</label>
			<input v-model="apellido" type="text" name="correo" id="micorreo" placeholder="Escribe tu apellido...">		

		<label>Edad:</label> 
			<input v-model.number="edad" type="text" name="numero" id="numero" placeholder="Captura tu edad...">		
			
		<label>Grado acádemico:</label>
				<select v-model="grado" name="select">
						<option value="secundaria" selected>Secundaria</option>
						<option value="primaria" >Primaria</option>
						<option value="licenciatura">Licenciatura</option>
						<option value="doctorado">Doctorado</option>
						<option value="tecnica">Carrera Técnica</option>
						<option value="maestria">Maestria</option>
						<option value="postgrado">Posgrado</option>
				</select>
<br/>				
		<label>Lenguaje de Programación Favorito:</label>
				<select v-model="lenguaje" name="select">
						<option value="javascript" selected>JavaScript</option>
						<option value="php" >PHP</option>
						<option value="c#">C#</option>
						<option value="c++">C++</option>
            <option value="python">Python</option>
            <option value="java">Java</option>
				</select>
<div class="form-group mt-2">
<button class="btn btn-success"> Agregar </button>
</div>
	
  
</form>
<br/>
<br/>
<br/>


  <table class="table">
  <thead>
    <tr>
      <th scope="col">Nombre</th>
      <th scope="col">Apellido</th>
      <th scope="col">Edad</th>
      <th scope="col">Grado</th>
      <th scope="col">Lenguaje</th>
      <th scope="col"> Acciones</th>
    </tr>
  </thead>
  <tbody >
    <tr v-for="(alumno, index) in alumnos" :key="index">
      <td> {{alumno.nombre}} </td>
      <td>{{alumno.apellido}}</td>
      <td>{{alumno.grado}}</td>
      <td>{{alumno.edad}}</td>
      <td>{{alumno.lenguaje}}</td>
      <button class="btn btn-danger" @click="eliminar(index)">X</button>
    </tr>
 
  </tbody>
</table>
  
</div>
</template>

<script>

export default {
  name: 'HelloWorld',
 
  data () {
    return {
      nombre: '',
      apellido: '',
      edad : null,
      grado: '',
      alumnos: [
        {"nombre": "Jose", "apellido": "Lopez", "edad" : 22, "grado": "Preparatoria", "lenguaje" : "PHP"},
        {"nombre": "David", "apellido": "Olea", "edad" : 32, "grado": "Maestria", "lenguaje" : "C++"},
        {"nombre": "Maria", "apellido": "Miller", "edad" : 25, "grado": "Licenciatura", "lenguaje" : "Python"},
        {"nombre": "Efraín", "apellido": "Rincon", "edad" : 27, "grado": "Licenciatura", "lenguaje" : "Java"},
        {"nombre": "Mario", "apellido": "Cruz", "edad" : 24, "grado": "Licenciatura", "lenguaje" : "Python"},
        {"nombre": "Luis", "apellido": "Espinoza", "edad" : 26, "grado": "Licenciatura", "lenguaje" : "PHP"},
        {"nombre": "Alejandro", "apellido": "Juarez", "edad" : 35, "grado": "Licenciatura", "lenguaje" : "C"},
        {"nombre": "Marcos", "apellido": "Castro", "edad" : 33, "grado": "Maestria", "lenguaje" : "C#"},
        {"nombre": "Javier", "apellido": "Guardado", "edad" : 22, "grado": "Licenciatura", "lenguaje" : "PHP"},
        {"nombre": "Jesus", "apellido": "Veliz", "edad" : 20, "grado": "Licenciatura", "lenguaje" : "JavaScript"},
      ]
    }
  },
  methods: {
    agregar(){
      let nuevo = {
        nombre : this.nombre,
        apellido : this.apellido,
        edad : this.edad,
        grado : this.grado,
        lenguaje : this.lenguaje
      }
      this.$emit('submit', nuevo)
      this.alumnos.push(nuevo)
      this.nombre = ''
      this.apellido = ''
      this.edad = null
      this.grado = ''
      this.lenguaje = ''
    },
    eliminar(index){
      this.alumnos.splice(index,1)
      console.log(index)
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
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
