<template>
  <div class="container">
    <div class="card">
      <div class="card-header">
        <h3>Add New Employee</h3>
      </div>
      <div class="card-body">
        <form @submit.prevent="createNewEmployee">
          <!-- inicio bloco: employee name -->
          <div class="form-floating mb-3">
            <input
            type="text"
            class="form-control"
            placeholder="Type your name"
            v-model="employee.name"
            />
            <label class="floatingInput" for="employee-name">Employee Name</label>
          </div>
          <!-- fim bloco: employee name -->
          <!-- inicio bloco: Job Role -->
          <div class="form-floating mb-3">
            <input
            type="text"
            class="form-control"
            placeholder="Type your job role"
            v-model="employee.job_role"
            />
            <label class="floatingInput" for="job-role">Job Role</label>
          </div>
          <!-- fim bloco: Job Role -->
          <!-- inicio bloco: Salary -->
          <div class="form-floating mb-3">
            <input
            type="text"
            class="form-control"
            placeholder="Type your salary"
            v-model="employee.salary"
            />
            <label class="floatingInput" for="salary">Salary</label>
          </div>
          <!-- fim bloco: Salary -->
          <!-- inicio bloco: Birth -->
          <div class="form-floating mb-3">
            <input
            type="date"
            class="form-control"
            placeholder="YYYY/MM/DD"
            v-model="employee.birth"
            />
            <label class="floatingInput" for="birth">Birth</label>
          </div>
          <!-- fim bloco: Birth -->
          <!-- inicio bloco: Employee Registration -->
          <div class="form-floating mb-3">
           <input
            type="text"
            class="form-control"
            placeholder="Type your Employee Registration"
            v-model="employee.employee_registration"
            />
            <label
            class="floatingInput"
            for="employee-registration">
            Employee Registration
          </label>
          </div>
          <!-- fim bloco: Employee Registration -->
          <div class="mb-3">
            <button
              type="submit"
              class="btn btn-primary">+ Employee
            </button>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'CreateEmployeeComponent',
  data() {
    return {
      employee: {
        name: '',
        job_role: '',
        salary: '',
        birth: '',
        employee_registration: '',
      },
    };
  },
  methods: {
    handleSubmitForm() {
      // implementar a logica do botao
    },
  },
};
</script>
