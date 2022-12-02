
<template>
  <div class="project">
    <h1>Mon portfiolio</h1>
  </div>
  <div class="menu">
    <a href="http://localhost:3000/">Homepage</a>
  </div>
  <div class="github_info">
    <h2>mes projets</h2>
    <ul>
      <li v-for="item in data">
        <a :href="item.html_url">
          <h1>{{item.name}}</h1>
        </a>
      </li>
    </ul>
  </div>
</template>

<script setup>
  let data = await $fetch('/api/github');
</script>


<style>
.github_info {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
}
ac{
  text-decoration: underline;
}
.project {
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  width: 100vw;
  height: 100vh;
  background-color: #344D59;
  background-size: cover;
}
a:hover {
  border-bottom-style: dot-dash;
  background-color: #B8CBD0;
}

.menu {
  display: flex;
  justify-content: right;
  align-items: first baseline;
  position: absolute;
  background-color: #7A90A4;
  flex-direction: column;
  font-size: 20px;
  top : 0;
  height: 50px;
  width: 150px;
  line-height: 40px;
  text-align: center;
  -moz-text-size-adjust: auto;
}

</style>
