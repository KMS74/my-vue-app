<template lang="">
  <div v-if="students.length > 0">
    <div class="table-responsive">
      <table class="table table-light">
        <thead>
          <tr>
            <th scope="col">Id</th>
            <th scope="col">Name</th>
            <th scope="col">City</th>
            <th scope="col">Actions</th>
          </tr>
        </thead>
        <tbody>
          <tr v-for="student in students" :key="student.id" class="">
            <td scope="row">{{ student.id }}</td>
            <td>{{ student.name }}</td>
            <td>{{ student.city }}</td>
            <td class="d-flex flex-row align-items-center gap-4">
              <button class="btn btn-outline-primary btn-sm">
                <i class="bi bi-pencil-fill"></i>
              </button>
              <button v-on:click="removeStudent(student.id)" class="btn btn-outline-danger btn-sm">
                <i class="bi bi-trash3-fill"></i>
              </button>
            </td>
          </tr>
        </tbody>
      </table>
    </div>
    <BaseModel>
      <template #header>
        <h5 class="modal-title" id="modalTitleId">Adding New Student</h5>
      </template>
      <template #student-form>
        <form>
          <div class="mb-3">
            <label for="name" class="form-label">Name</label>
            <input type="text" id="name" class="form-control" v-model="name" />
          </div>
          <div class="mb-3">
            <label for="city" class="form-label">Name</label>
            <input type="text" id="city" class="form-control" v-model="city" />
          </div>
        </form>
      </template>
      <template #model-buttons>
        <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
        <button
          v-on:click="addStudent"
          type="submit"
          data-bs-dismiss="modal"
          class="btn btn-primary"
        >
          Add
        </button>
      </template>
    </BaseModel>
  </div>

  <p v-else class="alert alert-warning text-center w-50" role="alert">
    Students tabel is empty! Try add some students
  </p>
</template>
<script>
import BaseModel from './BaseModel.vue'
export default {
  data() {
    return {
      students: [
        {
          id: 1,
          name: 'Karem',
          city: 'Cairo'
        },
        {
          id: 2,
          name: 'Mohamed',
          city: 'Alex'
        },
        {
          id: 3,
          name: 'Ali',
          city: 'Giza'
        }
      ],
      name: '',
      city: ''
    }
  },
  methods: {
    addStudent() {
      console.log('submit')
      if (this.name.length > 0 && this.city.length > 0) {
        this.students.push({
          id: this.students.length + 1,
          name: this.name.trim(),
          city: this.city.trim()
        })
      }
      this.name = ''
      this.city = ''
    },
    removeStudent(id) {
      this.students = this.students.filter((student) => student.id !== id)
    }
  },
  components: {
    BaseModel
  }
}
</script>
<style lang=""></style>
