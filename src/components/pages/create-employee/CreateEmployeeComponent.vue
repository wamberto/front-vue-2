<template>
  <div class="container">
    <div class="card">
      <div class="card-header">
        <h3>Add New Employee</h3>
      </div>
      <div class="card-body">
        <form @submit.prevent="handleSubmitForm()">
          <!-- inicio bloco: employee name -->
          <div class="form-floating mb-3">
            <input
            type="text"
            id="name"
            name="name"
            class="form-control"
            placeholder="Type your name"
            v-model="employeeForm.name"
            :class="{ 'is-invalid' : isSubmitted && $v.employeeForm.name.$error }"
            />
            <div
            v-if="isSubmitted && !$v.employeeForm.name.required"
            class="invalid-feedback"
            >
            Employee Name is Required
            </div>
            <label class="floatingInput" for="employee-name">Employee Name</label>
          </div>
          <!-- fim bloco: employee name -->
          <!-- inicio bloco: Job Role -->
          <div class="form-floating mb-3">
            <input
            type="text"
            id="job_role"
            name="job_role"
            class="form-control"
            placeholder="Type your job role"
            v-model="employeeForm.job_role"
            :class="{ 'is-invalid' : isSubmitted && $v.employeeForm.job_role.$error }"
            />
            <div
            v-if="isSubmitted && !$v.employeeForm.job_role.required"
            class="invalid-feedback"
            >
            Job Role is Required
            </div>
            <label class="floatingInput" for="job-role">Job Role</label>
          </div>
          <!-- fim bloco: Job Role -->
          <!-- inicio bloco: Salary -->
          <div class="form-floating mb-3">
            <input
            type="text"
            id="salary"
            name="salary"
            class="form-control"
            placeholder="Type your salary"
            v-model="employeeForm.salary"
            :class="{ 'is-invalid' : isSubmitted && $v.employeeForm.salary.$error }"
            />
            <div
            v-if="isSubmitted && !$v.employeeForm.salary.required"
            class="invalid-feedback"
            >
            Salary is Required
            </div>
            <label class="floatingInput" for="salary">Salary</label>
          </div>
          <!-- fim bloco: Salary -->
          <!-- inicio bloco: Birth -->
          <div class="form-floating mb-3">
            <input
            type="date"
            id="birth"
            name="birth"
            class="form-control"
            placeholder="YYYY/MM/DD"
            v-model="employeeForm.birth"
            :class="{ 'is-invalid' : isSubmitted && $v.employeeForm.birth.$error }"
            />
            <div
            v-if="isSubmitted && !$v.employeeForm.birth.required"
            class="invalid-feedback"
            >
            Birth is Required
            </div>
            <label class="floatingInput" for="birth">Birth</label>
          </div>
          <!-- fim bloco: Birth -->
          <!-- inicio bloco: Employee Registration -->
          <div class="form-floating mb-3">
           <input
            type="text"
            id="employee_registration"
            name="employee_registration"
            class="form-control"
            placeholder="Type your Employee Registration"
            v-model="employeeForm.employee_registration"
            :class="{ 'is-invalid' : isSubmitted && $v.employeeForm.employee_registration.$error }"
            />
            <div
            v-if="isSubmitted && !$v.employeeForm.employee_registration.required"
            class="invalid-feedback"
            >
            Employee Registration is Required
            </div>
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

import { required } from 'vuelidate/lib/validators';

export default {
  name: 'CreateEmployeeComponent',
  data() {
    return {
      employeeForm: {
        name: '',
        job_role: '',
        salary: '',
        birth: '',
        employee_registration: '',
      },
      isSubmitted: false,
    };
  },
  validations: {
    employeeForm: {
      name: { required },
      job_role: { required },
      salary: { required },
      birth: { required },
      employee_registration: { required },
    },
  },
  methods: {
    handleSubmitForm() {
      this.isSubmitted = true;

      this.$v.$touch();
      if (this.$v.$invalid) {
        return;
      }
    },
  },
};
</script>
