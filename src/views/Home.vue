<template>
  <div class="home">
    <h1>All Students</h1>
    <div v-for="student in students" v-bind:key="student.id">
      <h2>Name: {{ student.name }}</h2>
      <h2>Resume: {{ student.resume }}</h2>
      <h2>Twitter: {{ student.twitter }}</h2>
      <button v-on:click="showStudent(student)">More info</button>
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
  </div>
</template>

<style></style>

<script>
// import axios from "axios";
export default {
  data: function () {
    return {
      students: [
        { id: 1, name: "Jill", resume: "Worked on a crab boat", twitter: "twitter.com/jill35" },
        { id: 2, name: "Jack", resume: "Worked on a rad boat", twitter: "twitter.com/jack32" },
        { id: 3, name: "Ryan", resume: "Very handsome", twitter: "twitter.com/simmz53" },
      ],
      currentStudent: [{ id: 3, name: "Ryan", resume: "Very handsome", twitter: "twitter.com/simmz53" }],
    };
  },

  // created: function () {
  //   this.indexStudents();
  // },
  methods: {
    // indexStudents: function () {
    //   axios.get("/students").then((response) => {
    //     console.log("students index", response);
    //     this.students = response.data;
    //   });
    // },
    showStudent: function (student) {
      this.currentStudent = student;
      document.querySelector("#student-details").showModal();
    },
  },
};
</script>
