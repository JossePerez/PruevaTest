<template>
        <article class="container text-center">
        <div class="row">
            <div class="col-ms-12 col-md-6 col-lg-4 col-xl-4">
                <div class="div-foro" >
                    <div class="div-foro-circular">
                        <!-- Cargar un img -->
                    </div>
                    <div class="div-foro-info">
                        <h3>Nombre</h3>
                        <p>Edad</p>
                        <p>Email</p>
                    </div>
                </div>
            </div>
            <div class="col-ms-12 col-md-6 col-lg-4 col-xl-4">
                <div class="div-foro" >
                    <div class="div-foro-circular">
                        <!-- Cargar un img -->
                    </div>
                    <div class="div-foro-info">
                        <h3>Nombre</h3>
                        <p>Edad</p>
                        <p>Email</p>
                    </div>
                </div>
            </div>
            <div class="col-ms-12 col-md-6 col-lg-4 col-xl-4">
                <div class="div-foro" >
                    <div class="div-foro-circular">
                        <!-- Cargar un img -->
                    </div>
                    <div class="div-foro-info">
                        <h3>Nombre</h3>
                        <p>Edad</p>
                        <p>Email</p>
                    </div>
                </div>
            </div>
        </div>
    </article>
</template>

<script>
export default{

}
import 'bootstrap/dist/js/bootstrap.js';
</script>

<style>
.div-foro{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.div-foro-circular{
    width: 10rem;
    height: 10rem;
    border-radius: 100%;
    background-color: rgb(16, 86, 218);
}

.div-foro-info{
    color: #202020;
}
</style>