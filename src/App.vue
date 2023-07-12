<template>
  <Header />
  <main>
    <h1 class="title-content">Inputs</h1>
    <div class="inputs-styles-section">
      <ul class="inputs-styles-list" id="default">
        <li class="input-style-item">
          <span class="style-name">Input</span>
          <Input 
            :labelName="'Label'" 
            :placeholderInput="'Placeholder'"
          />
        </li>
        <li class="input-style-item">
          <span class="style-name">&:hover</span>
          <Input 
            class="on-hover"  
            :labelName="'Label'" 
            :placeholderInput="'Placeholder'"
          />
        </li>
        <li class="input-style-item">
          <span class="style-name">&:focus</span>
          <Input 
            :labelName="'Label'" 
            :placeholderInput="'Placeholder'"
            class="on-focus"
          />
        </li>
      </ul>
    </div>

    <span class="icon-link">
      Icons: https://material.io/resources/icons/?style=round
    </span>
  </main>
  <footer>created by Nehuen - devChallenges.io</footer>
</template>

<script >
  import Header from './components/UI/Header.vue';
  import Input from './components/UI/Input.vue';
  export default {
    name: 'App',
    components: {
      Header,
      Input
    }
  }
</script>

<style>

main .title-content {
  font: 500 1.5rem 'Poppins', sans-serif;
  color: #4F4F4F;
}

.inputs-styles-section {
  display: flex;
  flex-direction: column;
  row-gap: 5vh;
}

ul.inputs-styles-list {
  width: 100%;
  display: flex;
  flex-wrap: wrap;
  gap: 3vh 2vw;
}

.inputs-styles-list li.input-style-item {
  display: flex;
  flex-direction: column;
  row-gap: 1vh;
}

li.input-style-item .style-name {
  font: 400 14px 'Ubuntu Mono', monospace;
}

.icon-link {
  font: 400 12px 'Ubuntu Mono', monospace;;
  color: #828282;
}

footer {
  grid-area: footer;
  color: #A9A9A9;
  font: 700 14px 'Montserrat', sans-serif;
}

</style>
