<script>
import axios from "axios";
let API_URL = `/api/guardarPersonasUxd.php`; //HACE LA CONEXION CON LA API
export default {
    data() {
        return {
            nombre: "", 
            edad: "",
            estadoCivil: "",
            trabajo: "", //GUARDARA LOS DATOS QUE SE INGRESARAN
            residencia: "",
            cita: "",
            citaAutor: "",
            bio: "",
            personalidad01: "",
            personalidad02: "",
            personalidad03: "",
            personalidad04: "",
            objetivos: "",
            frustraciones: "",
            motivaciones: "",
            porcentaje: "",
            marcas: "",
        };
    },
    methods: {
        recibir() {
            API_URL + this.pagina;
            console.log(API_URL);
            axios.get("/api/guardarPersonasUxd.php", {
                nombre: nombre, //METODO DEL AXIOS PARA REALIZAR EL ENVIO DE LOS DATOS
                //completar las variables, estas deben llamarse como las que se recibirán en el backend sin el símbolo del dolar $
            })
                .then((response) => {
                    console.log(response.status)
                });
        },
    },
};

</script>
<template>
    <div>
        <button 
        @click="data()" class="button bg-green-700 rounded-full hover:outline outline-blue-600 hover:bg-green-500 w-20 text-zinc-100 hover:text-white">
            <strong>Ver</strong>
        </button>
        <input v-model="nombre" type="text">
    </div>
</template>