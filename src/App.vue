<template>
  <div id="app">
    <div id="header">
      <img src="./assets/bg-desktop-light.jpg">
    </div>
    <div id="content">
      <div class="row">
        <h1>Todo</h1>
        
        <div id="themeSwitch">
          <img src="./assets/icon-sun.svg" alt="sun">
          <img src="./assets/icon-moon.svg" alt="moon">
        </div>
      </div>

      <todoform/>

      <todolist
        :listToShow="this.list"/>
    </div>
  </div>
</template>

<script>
import todolist from './components/todolist.vue'
import todoform from './components/todoform.vue'

export default {
  name: 'App',
  components: {
    todolist,
    todoform
  },
  data() {
    return {
      list: [
        {"id": 1, "task": "Task1"},
        {"id": 2, "task": "Task2"},
        {"id": 3, "task": "Task3"}
      ],
      completed: [],
      active: [],
    }
  }
}
</script>

<style>
@import url('https://fonts.googleapis.com/css2?family=Josefin+Sans:wght@400;700&display=swap');

:root {
  --primary-blue: hsl(220, 98%, 61%);
  --background-gradient: linear-gradient(150deg, hsl(192, 100%, 67%), hsl(280, 87%, 65%));
  /* Light Theme */
  --l-very-light-grey: hsl(0, 0%, 98%);
  --l-very-light-grey-blue: hsl(236, 33%, 92%);
  --l-light-grey-blue: hsl(233, 11%, 84%);
  --l-dark-grey-blue: hsl(236, 9%, 61%);
  --l-very-dark-grey-blue: hsl(235, 19%, 35%);
  /* Dark Theme */
  --d-very-dark-blue: hsl(235, 21%, 11%);
  --d-very-dark-desa-blue: hsl(235, 24%, 19%);
  --d-light-grey-blue: hsl(234, 39%, 85%);
  --d-light-grey-blue-hover: hsl(236, 33%, 92%);
  --d-dark-grey-blue: hsl(234, 11%, 52%);
  --very-dark-grey-blue: hsl(233, 14%, 35%);
  --even-darker-grey-blue: hsl(237, 14%, 26%);
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: 'Josefin Sans', sans-serif;
  font-size: 18px; 
}

html, body {
  height: 100%;
}

#app {
  height: 100%;
  display: flex;
  justify-content: center;
}

#header {
  position: absolute;
  width: 100%;
  height: 300px;
  z-index: 50;
}

#header img {
  object-fit: cover;
  width: 100%;
  height: 100%;
}

#content {
  padding-top: 50px;
  position: relative;
  z-index: 100;
  width: 40%;
}

.row {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h1 {
  font-size: 40px;
  text-transform: uppercase;
  letter-spacing: 15px;
  color: var(--l-very-light-grey)
}

.flip-list-move {
  transition: transform 0.5s;
}
.no-move {
  transition: transform 0s;
}
.ghost {
  opacity: 0.5;
  background: #dcdcdc;
}
.list-group {
  min-height: 20px;
}
.list-group-item {
  cursor: pointer;
  list-style-type: none;
}
</style>
