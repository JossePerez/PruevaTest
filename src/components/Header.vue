<template>
        <header>
        <figure class="imagen-con-texto header-imagen">
            <img src="../assets/universo.jpg" alt="Foto Principal" class="img-fluid">
            <figcaption class="texto-imagen">
                <div class="div-cuadro"></div>
            </figcaption>
        </figure>
    </header>
</template>

<script>
export default{

}
import 'bootstrap/dist/js/bootstrap.js';
</script>

<style>
    .header-imagen{ 
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    .header-imagen img{
        width: 100%;
        height: 15rem;
    }

    .div-cuadro{
        width: 4rem;
        height: 1.5rem;
        background-color: green;
        border-top-left-radius: 15px;
        border-bottom-left-radius: 15px;
        border-top-right-radius: 15px;
        border-bottom-right-radius: 15px;
    }
    </style>