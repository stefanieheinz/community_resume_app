<template>
  <div id="app">
    <div id="nav">
      <router-link to="/">Home</router-link>
      |
      <router-link to="/about">About</router-link>
    </div>
    <router-view />
  </div>
</template>

<style>
/* RESET */
body {
  margin: 0;
  padding: 0;
}

/* CENTERING */
main {
  margin: 0 auto;
  max-width: 50em;
}

/* FONT */
body {
  font-family: "Roboto", "Helvetica", "Arial", sans-serif;
}

/* SPACING */
main {
  line-height: 1.5;
  padding: 4em 1em;
}

h2 {
  margin-top: 1em;
  padding-top: 1em;
}

/* COLOR */
body {
  color: #0c5583;
}

h1,
h2 {
  color: rgb(18, 150, 14);
  text-align: center;
}
p {
  color: #751bb1;
  text-align: center;
}

button {
  color: rgb(255, 255, 255);
  background-color: black;
  height: 34px;
  position: relative;
}

a {
  color: #e81c4f;
}

/* HEADER */
html {
  background-color: #40db7b;
  background-image: url("https://images.unsplash.com/photo-1582284168532-ef7b89baa1c8?ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&ixlib=rb-1.2.1&auto=format&fit=crop&w=1901&q=80");
  background-position: center top;
  background-repeat: no-repeat;
  background-size: cover;
  line-height: 1.2;
  padding: 32vw 2em;
  text-align: center;
}

header h1 {
  color: rgb(138, 4, 4);
  font-size: 2.5em;
  font-weight: 300;
}

header a {
  border: 1px solid #e81c4f;
  border-radius: 2em;
  color: white;
  font-size: 0.6em;
  letter-spacing: 0.2em;
  padding: 1em 2em;
  text-transform: uppercase;
  text-decoration: none;
  transition-property: color, background;
  transition-duration: 200ms;
}

header a:hover {
  background: #e81c4f;
  color: white;
}
</style>
