<template>
  <div class="home">
    <h1>New Student</h1>
    <div>
      Name:
      <input type="text" v-model="newStudent.name" />
      Resume:
      <input type="text" v-model="newStudent.resume" />
      Twitter:
      <input type="text" v-model="newStudent.twitter" />
      <button v-on:click="createStudent()">Create Student</button>
    </div>

    <h1>All Students</h1>
    <div v-for="student in students" v-bind:key="student.id">
      <h2>{{ student.name }}</h2>
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
      newStudent: {},
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
    createStudent: function () {
      var params = {
        name: this.newStudent.name,
        resume: this.newStudent.resume,
        twitter: this.newStudent.twitter,
      };
      axios
        .post("/students", params)
        .then((response) => {
          console.log("students create", response);
          this.students.push(response.data);
          this.newStudent = {};
        })
        .catch((error) => {
          console.log("students create error", error.response);
        });
    },
  },
};
</script>
