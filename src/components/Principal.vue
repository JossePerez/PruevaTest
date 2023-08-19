<template>
    <!--Aqui va el componente principal-->
    <article class="container text-center">
        <div class="row div-orden">
            <div class="col-ms-12 col-md-6 col-lg-4 col-xl-4" v-for="job in jobs" :key="job._id">
                <div class="div-card">
                    <div class="card-main">
                       <div class="div-image-card">
                           <img src="../assets/HomeEmpresas.jpg" alt="" class="img-fluid">
                       </div>
                       <div>
                           <br>
                           <h3>{{ job.company }}</h3>
                           <p>{{ job.job }}</p>
                           <p><span>$</span>{{ job.payment }}<span> Pesos</span></p>
                       </div>
                    </div>
                    <div class="div-card-bottom">
                        <div>
                            <button type="button" class="btn btn-warning" data-toggle="modal" :data-target="'#editModal-' + (editingJob ? editingJob._id : '')" @click="editJob(job)">Modificar</button>
                        </div>  
                        <div>
                            <button type="button" class="btn btn-danger" @click="deleteJob(job._id)">Eliminar</button>
                        </div>
                    </div>
                </div>
            </div>
        </div>
        
        <!-- Modal de edición -->
        <div class="modal fade" :id="'editModal-' + (editingJob ? editingJob._id : '')" tabindex="-1" role="dialog" aria-labelledby="editModalLabel" aria-hidden="true">
            <div class="modal-dialog" role="document">
                <div class="modal-content">
                    <div class="modal-header">
                        <h5 class="modal-title" id="editModalLabel">Editar Trabajo</h5>
                        <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                            <span aria-hidden="true">&times;</span>
                        </button>
                    </div>
                    <div class="modal-body">
                        <label for="edit-company">Compañía:</label>
                        <input v-if="editingJob" type="text" id="edit-company" v-model="editingJob.company" class="form-control" />
                                            
                        <label for="edit-job">Trabajo:</label>
                        <input v-if="editingJob" type="text" id="edit-job" v-model="editingJob.job" class="form-control" />
                                            
                        <label for="edit-payment">Pago:</label>
                        <input v-if="editingJob" type="number" id="edit-payment" v-model="editingJob.payment" class="form-control" />

                    </div>
                    <div class="modal-footer">
                        <button type="button" class="btn btn-secondary" data-dismiss="modal">Cancelar</button>
                        <button type="button" class="btn btn-primary" @click="saveEditedJob">Guardar Cambios</button>
                    </div>
                </div>
            </div>
        </div>
    </article>
</template>

<script>
import axios from 'axios';
import 'bootstrap/dist/js/bootstrap.js';

export default {
    data() {
        return {
            jobs: [],
            editingJob: null,
        };
    },
    mounted() {
        this.fetchJobs();
    },
    methods: {
        async fetchJobs() {
            try {
                const response = await axios.get('http://localhost:9000/api/jobs');
                this.jobs = response.data;
            } catch (error) {
                console.error('Error al obtener las empresas:', error);
            }
        },
        editJob(job) {
            this.editingJob = job;
        },
        async saveEditedJob() {
            try {
                await axios.put(`http://localhost:9000/api/jobs/${this.editingJob._id}`, this.editingJob);
                console.log('Trabajo editado:', this.editingJob);
                this.fetchJobs(); // Actualiza la lista después de editar
                this.editingJob = null; // Limpia el trabajo en edición
                $('#editModal-' + this.editingJob._id).modal('hide'); // Cierra el modal
            } catch (error) {
                console.error('Error al editar el trabajo:', error);
            }
        },
        async deleteJob(jobId) {
            try {
                await axios.delete(`http://localhost:9000/api/jobs/${jobId}`);
                this.fetchJobs(); // Actualiza la lista después de eliminar
            } catch (error) {
                console.error('Error al eliminar el trabajo:', error);
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