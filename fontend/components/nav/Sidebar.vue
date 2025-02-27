<template>
  <div class="bg-red" id="sider">
    <a href="#" class="logo">Logo</a>
    <nav class="navbar">
      <ul>
        <li><a href="">ABOUT ME</a></li>
        <li><a href="">SERVICES</a></li>
        <li><a href="">PORTFOLIO</a></li>
        <li><a href="">TESTIMONIALS</a></li>
        <li><a href="">CONTACT ME</a></li>
      </ul>
    </nav>
    <a href="" class="btn">HeirMe</a>
  </div>
</template>

<style scoped>
.bg-red {
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: wheat;
  color: rgb(8, 2, 2);
  padding: 10px;
  width: 100%;
}
.navbar ul {
  display: flex;
}
li a {
  margin: 35px;
}
.btn {
  background-color: aqua;
  padding: 10px 30px;
  border-radius: 5px;
  background: #fcc028;
}
</style>
