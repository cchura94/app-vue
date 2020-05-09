<template>
    <div class="container">        
        <div class="row">
            <div class="col-md-6">
                <h1>Venta de Productos</h1> 
                <div class="row">
                    <div class="col-md-4" v-for="(prod, index) in productos" :key="index">

                        <div class="card" style="width: 10rem;">
                            <img src="../assets/logo.png" class="card-img-top" alt="...">
                            <div class="card-body">
                                <h5 class="card-title">{{ prod.nombre }}</h5>
                                <p class="card-text">{{ prod.precio }}</p>
                                <button class="btn btn-primary" @click="agregar(prod)">agregar</button>
                            </div>
                        </div>

                    </div>
                </div>            

            </div>
            <div class="col-md-6">
                <h1>CArrito:</h1>
                <div class="card" >
                    <ul class="list-group list-group-flush">
                        <li class="list-group-item" v-for="(c, index) in carrito" :key="index">
                            {{ c.nombre }} - Bs. {{ c.precio }}

                            <button @click="eliminar(c)">x</button>
                        </li>
                    </ul>
                    <h1>Total: {{ total }}</h1>
                    <code>
                        {{ $data }}
                    </code>
                    
                </div>

            </div>
        </div>

        
    </div>
</template>

<script>
export default {
    data(){
        return {
            productos: [
                {nombre: "Mesa", precio: 350, imagen: "img.jpg", cantidad: 6},
                {nombre: "Silla", precio: 250, imagen: "img.jpg", cantidad: 12},
                {nombre: "Televisor", precio: 2350, imagen: "img.jpg", cantidad: 6},
                {nombre: "Radio", precio: 1250, imagen: "img.jpg", cantidad: 5},
                {nombre: "Mochila", precio: 450, imagen: "img.jpg", cantidad: 6}
            ],
            carrito: [],
            total: 0
        }
    },
    methods:{
        agregar(prod){
            this.total += prod.precio;
            this.carrito.push({nombre: prod.nombre, precio: prod.precio, imagen: prod.imagen, cantidad: 1})
        },
        eliminar(prod){
            alert("eliminar")
        }
    },


}
</script>






<style>

</style>