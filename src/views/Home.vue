<template>
  <div class="home">
    <h1>All Students</h1>
    <div v-for="student in students" v-bind:key="student.id">
      <p>First name: {{ student.first_name }}</p>
      <p>Last name: {{ student.last_name }}</p>
      <p>Email: {{ student.email }}</p>
      <button v-on:click="showStudent(student)">More info</button>
    </div>
    <dialog id="student-details">
      <form method="dialog">
        <h1>Student info</h1>
        <p>Phone Number: {{ currentStudent.phone_number }}</p>
        <p>Bio: {{ currentStudent.bio }}</p>
        <p>LinkedIn: {{ currentStudent.linkedin }}</p>
        <p>Twitter Handle: {{ currentStudent.twitter_handle }}</p>
        <p>Website: {{ currentStudent.website }}</p>
        <p>Resume URL: {{ currentStudent.resume_url }}</p>
        <p>Github: {{ currentStudent.github }}</p>
        <p>Photo: {{ currentStudent.photo }}</p>
        <button>Close</button>
      </form>
    </dialog>
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
