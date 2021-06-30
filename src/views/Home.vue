<template>
  <div class="home">
    <button v-on:click="showStudent(student)">Find Student</button>

    <h1>All Students</h1>
    <div v-for="student in students" v-bind:key="student.id">
      <h2>{{ student.name }}</h2>
    </div>
    <dialog id="student-details">
      <form method="dialog">
        <h1>Student info</h1>
        <p>Name: {{ currentStudent.name }}</p>
        <p>Resume: {{ currentStudent.resume }}</p>
        <p>Twitter: {{ currentStudent.twitter }}</p>
        <button>Close</button>
      </form>
    </dialog>
    <div>
      <h3>Search</h3>
      <p></p>
    </div>
  </div>
</template>

<style></style>

<script>
import axios from "axios";
export default {
  data: function () {
    return {
      students: [],
      currentStudent: {},
    };
  },
  created: function () {
    this.indexStudents();
  },
  methods: {
    indexStudents: function () {
      axios.get("/students").then((response) => {
        console.log("students index", response);
        this.students = response.data;
      });
    },
    showStudent: function (student) {
      this.currentStudent = student;
      document.querySelector("#student-details").showModal();
    },
  },
};
</script>
