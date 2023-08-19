<template>
    <!--Aqui va el componente principal-->
    <article class="container text-center">
        <div class="row div-orden">
            <div class="col-ms-12 col-md-6 col-lg-4 col-xl-4" v-for="job in jobs" :key="job._id">
                <div class="div-card">
                    <div class="card-main">
                       <div style="background-color: blue;" class="div-image-card">
                           <img src="../assets/logo.png" alt="" class="img-fluid">
                       </div>
                       <div>
                           <br>
                           <h3>{{ job.company }}</h3>
                           <p>{{ job.job }}</p>
                           <p>{{ job.payment }}</p>
                       </div>
                    </div>
                    <div class="div-card-bottom">
                        <div>
                            <button type="button" class="btn btn-warning">Modificar</button>
                        </div>  
                        <div>
                            <button type="button" class="btn btn-danger">Eliminar</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>

    </article>
</template>

<script>
    import axios from 'axios';
    import 'bootstrap/dist/js/bootstrap.js';
export default{
    data() {
    return {
      jobs: [],
    };
  },
  mounted() {
    this.fetchJops();
  },
  methods: {
    async fetchJops() {
      try {
        const response = await axios.get('http://localhost:9000/api/jobs');
        this.jobs = response.data;
      } catch (error) {
        console.error('Error al obtener las empresas:', error);
      }
    },
  },
}
</script>

<style>
.div-card{  
    border-radius: 15px;
    border: 2px solid #5E6A73;
    padding: 0px;
    box-shadow: 0px 10px 15px #000000;
    margin-bottom: 35px;
}
.div-card-bottom{
    border-top: 2px solid #5E6A73;
    display: flex;
    justify-content: space-between;
    padding: 10px 10px 10px 10px;
}

.div-image-card{
    border-radius: 15px;
    margin: 10px 10px 0 10px!important;
}

</style>