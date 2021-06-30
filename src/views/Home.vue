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
// import axios from "axios";
export default {
  data: function () {
    return {
      students: [
        {
          id: 4,
          first_name: "Bob",
          last_name: "Ross",
          email: "like_a_bross@tet.com",
          password: "pasword",
          phone_number: "1-800-BO-ROSS",
          bio: "Just a happy little accident.",
          linkedin: "linkedin.com/bbross",
          twitter_handle: "like_abross",
          website: "bobros.com",
          resume_url: "drive.google.com/bobross-esume",
          github: "github.com/bbross",
          photo: "bros.jpg",
        },
        {
          id: 5,
          first_name: "Bill",
          last_name: "Doss",
          email: "like_a_bDoss@tet.com",
          password: "pasword",
          phone_number: "1-800-BO-Doss",
          bio: "Just a happy little accident.",
          linkedin: "linkedin.com/bbDoss",
          twitter_handle: "like_abDoss",
          website: "bobros.com",
          resume_url: "drive.google.com/bobDoss-esume",
          github: "github.com/bbDoss",
          photo: "bros.jpg",
        },
      ],
      currentStudent: {},
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
