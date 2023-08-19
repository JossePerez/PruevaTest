<template>
        <footer class="container-fluid">
        <div class="row footer-contenedor">
            <div class="col-5">
                <div class="footer-div-izquierdo">
                    <h3>Trabajos Mexico</h3>
                    <p>Encuentra el trabajo de tus sueños</p>
                </div>
            </div>
            <div class="col-7">
                <div class="footer-div-derecho">
                    <div>
                        <h4>Contactos</h4>
                        <p><span>Numero de Telefono:</span></p>
                        <p>(664) 987-65-43</p>
                        <p><span>Numero de Celular:</span></p>
                        <p>(663) 123-45-67</p>
                    </div>
                    <div>
                        <h4>Redes Sociales</h4>
                        <p><span>Email 1:</span></p>
                        <p>jose18@gmail.com</p>
                        <p><span>Email 2:</span></p>
                        <p>jesus25@gmail.com</p>
                    </div>
                </div>
            </div>
        </div>
    </footer>
</template>

<script>
export default{

}
import 'bootstrap/dist/js/bootstrap.js';
</script>

<style>
    /*Footer */
    .footer-contenedor{
        display: flex;
        align-items: center;
        background-color: #232323;
        color: white;
    }

    .footer-contenedor p{
        font-size: 14px;
    }

    .footer-div-izquierdo{
        margin: 1rem;
        display: flex;
        flex-direction: column;
        align-items: center;
        justify-content: center;
    }

    .footer-div-derecho{
        margin: 1rem;
        display: flex;
        justify-content: space-around;
    }

    .footer-div-derecho div span{
        font-weight: 800;
        font-size: 15px;
    }
</style>