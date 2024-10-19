<template>
    <div class="form-container mb-4">
      <form @submit.prevent="submitForm" class="row g-3">
        <div class="col-md-9">
          <label :class="{'text-danger': !appointment.paciente}" class="form-label">Paciente</label>
          <input type="text" v-model="appointment.paciente" class="form-control" />
        </div>
        <div class="col-md-3">
          <label :class="{'text-danger': !appointment.fecha}" class="form-label">Fecha</label>
          <input type="date" v-model="appointment.fecha" class="form-control" />
        </div>
        <div class="col-md-2">
          <label :class="{'text-danger': !appointment.hora}" class="form-label">Hora</label>
          <input type="time" v-model="appointment.hora" class="form-control" />
        </div>
        <div class="col-md-4">
          <label :class="{'text-danger': !appointment.gravedad}" class="form-label">Gravedad</label>
          <select v-model="appointment.gravedad" class="form-select">
            <option disabled value="">Selecciona una opción</option>
            <option value="baja">Baja</option>
            <option value="media">Media</option>
            <option value="alta">Alta</option>
          </select>
        </div>
        <div class="col-md-6">
          <label :class="{'text-danger': !appointment.motivo}" class="form-label">Motivo</label>
          <input type="text" v-model="appointment.motivo" class="form-control" />
        </div>
        <div class="col-12 text-center">
          <button type="submit" :disabled="!isFormValid" class="btn btn-primary">Agregar</button>
        </div>
      </form>
    </div>
  </template>
  
  <script>
  export default {
    data() {
      return {
        appointment: {
          paciente: '',
          fecha: '',
          hora: '',
          gravedad: '',
          motivo: ''
        }
      };
    },
    computed: {
      isFormValid() {
        return (
          this.appointment.paciente &&
          this.appointment.fecha &&
          this.appointment.hora &&
          this.appointment.gravedad &&
          this.appointment.motivo
        );
      }
    },
    methods: {
      submitForm() {
        this.$emit('add-appointment', { ...this.appointment });
        this.resetForm();
      },
      resetForm() {
        this.appointment = {
          paciente: '',
          fecha: '',
          hora: '',
          gravedad: '',
          motivo: ''
        };
      }
    }
  };
  </script>
  
  <style scoped>
  .text-danger {
    color: red;
  }
  .form-container {
    background-color: #f8f9fa;
    padding: 20px;
    border-radius: 10px;
    box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  }
  </style>
  