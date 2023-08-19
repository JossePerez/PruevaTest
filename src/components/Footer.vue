<template>
        <footer class="container-fluid">
        <div class="row footer-contenedor">
            <div class="col-5">
                <div class="footer-div-izquierdo">
                    <h4>Informacion de lo que se ve</h4>
                    <p>Lorem ipsum dolor sit, amet consectetur adipisicing elit. Laborum, esse.</p>
                </div>
            </div>
            <div class="col-7">
                <div class="footer-div-derecho">
                    <div>
                        <h4>Contactos</h4>
                        <p>Lorem ipsum dolor sit.</p>
                        <p>Lorem ipsum dolor sit.</p>
                    </div>
                    <div>
                        <h4>Redes Sociales</h4>
                        <p>Lorem ipsum dolor sit.</p>
                        <p>Lorem ipsum dolor sit.</p>
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
</style>