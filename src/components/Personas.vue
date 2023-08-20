<template>
    <article class="container text-center">
      <h1>Personas</h1>
      <br>
      <div class="row">
          <div class="col-ms-12 col-md-6 col-lg-4 col-xl-4" v-for="user in users" :key="user._id">
              <div class="div-foro" >
                  <div class="div-foro-circular">
                      <img src="../assets/cara.webp" alt="" class="img-fluid">
                  </div>
                  <div class="div-foro-info">
                      <h3>{{ user.name }}</h3>
                      <p>{{ user.age }}</p>
                      <p>{{ user.email }}</p>
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
      users: [],
    };
  },
  mounted() {
    this.fetchUsers();
  },
  methods: {
    async fetchUsers() {
      try {
        const response = await axios.get('http://localhost:9000/api/users');
        this.users = response.data;
      } catch (error) {
        console.error('Error al obtener usuarios:', error);
      }
    },
  },
};
</script>

<style>
.div-foro{
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    border-radius: 15px;
    border: 2px solid #5E6A73;
    padding: 0px;
    box-shadow: 0px 10px 15px #000000;
    margin: 35px;
    width: 15rem;
}
.div-foro-circular img{
    border-radius: 100%;
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