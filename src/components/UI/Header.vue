<template>
    <header>
      <div class="logo">
        <span class="orange">Dev</span>
        <span class="dark-blue">challenges.io</span>
      </div>
      <nav>
        <ul class="navbar">
          <li class="nav-item">
            <a class="nav-link" href="#">Typography</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Grid</a>
          </li>
          <li class="nav-item">
            <a class="nav-link" href="#">Buttons</a>
          </li>
          <li class="nav-item">
            <a class="nav-link active" href="#">Inputs</a>
          </li>
        </ul>
      </nav>
    </header>
  </template>
  
  <script>
  export default {
    name: 'Header',
  
  }
  </script>
  
  <style scoped>
  
  header {
    grid-area: header;
    height: 100vh;
    padding: 5vh;
    display: flex;
    flex-direction: column;
  }
  
  
  .logo span { font: 600 13px 'Poppins', sans-serif; }
  .logo .orange { color: #F7542E; }
  .logo .dark-blue { color: #090F31; }
  
  
  nav { height: 80%; }
  nav ul.navbar {
    margin-top: 10vh;
    font: 500 14px 'Noto Sans JP', sans-serif;
    display: flex;
    flex-direction: column;
    row-gap: 5vh;
  }
  
  ul.navbar .nav-item {
    color: #9E9E9E;
  }
  
  .nav-item:has(.nav-link.active) {
    font-weight: 700;
    color: #090F31;
  }
  </style>