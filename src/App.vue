<template>
  <div class="container mt-5">
    <appointment-form @add-appointment="addAppointment" />
    <div v-if="appointments.length === 0" class="text-center mt-3 text-danger">
      Aún no hay consultas registradas
    </div>

    <div class="row mt-3">
      <div v-for="(appointment, index) in appointments" :key="index" class="col-md-4 mb-4">
        <appointment-card
          :appointment="appointment"
          @delete-appointment="deleteAppointment(index)"
        />
      </div>
    </div>
  </div>
</template>

<script>
import AppointmentForm from './components/AppointmentForm.vue';
import AppointmentCard from './components/AppointmentCard.vue';

export default {
  components: {
    AppointmentForm,
    AppointmentCard
  },
  data() {
    return {
      appointments: []
    };
  },
  methods: {
    addAppointment(newAppointment) {
      this.appointments.push(newAppointment);
    },
    deleteAppointment(index) {
      this.appointments.splice(index, 1);
    }
  }
};
</script>

<style scoped>
.col-md-4 {
  padding: 0 15px; 
}

.row {
  margin-left: -15px; 
  margin-right: -15px;
}
</style>
