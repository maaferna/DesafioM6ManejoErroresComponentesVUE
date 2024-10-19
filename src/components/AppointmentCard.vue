<template>
    <div class="card h-100" :class="gravedadClass">
      <div class="card-body">

        <h5 class="card-title">Paciente</h5>
        <p><span class="value">{{ appointment.paciente }}</span></p>
        <hr class="hr-white"/> 
  
        <h6>Fecha</h6>
        <p><span class="value">{{ appointment.fecha }}</span></p>
        <hr class="hr-white"/> 
  
        <h6>Hora</h6>
        <p><span class="value">{{ appointment.hora }}</span></p>
        <hr class="hr-white"/> 
  
        <h6>Motivo</h6>
        <p><span class="value">{{ appointment.motivo }}</span></p>
      </div>
  
      <div class="card-footer text-center">
        <button @click="deleteAppointment" class="btn btn-danger">Eliminar</button>
      </div>
    </div>
  </template>
  
  <script>
  export default {
    props: {
      appointment: Object
    },
    computed: {
      gravedadClass() {
        switch (this.appointment.gravedad) {
          case 'baja':
            return 'bg-success text-light'; 
          case 'media':
            return 'bg-warning text-dark'; 
          case 'alta':
            return 'bg-danger text-light'; 
          default:
            return '';
        }
      }
    },
    methods: {
      deleteAppointment() {
        this.$emit('delete-appointment');
      }
    }
  };
  </script>
  
  <style scoped>
  .card {
    border-radius: 15px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  
  .hr-white {
    border: 1px solid white;
    margin: 10px 0;
  }
  
  .value {
    font-weight: bold;
    text-transform: uppercase; 
    color: white; 
  }
  
  .card-footer {
    background-color: rgba(0, 0, 0, 0.05);
  }
  </style>
  