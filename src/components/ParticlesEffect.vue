<script setup>

</script>

  <template>
    <div class="particles-container">
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
      <div class="particle"></div>
    </div>
  </template>

  <!--particles-container-->
  <style scoped>
  .particles-container{
    position: absolute;
    inset: 0;
    z-index: 1;
  }
  </style>

  <!--particle-->
  <style scoped>
  .particle {
    position: absolute;
    bottom: 0px;
    left: 50%;

    width: 30px;
    height: 30px;
    background-color: red;
    border-radius: 50%;
  }

  .particle:nth-child(1) { left: 30%; }
  .particle:nth-child(2) { left: 40%; }
  .particle:nth-child(3) { left: 50%; }
  .particle:nth-child(4) { left: 60%; }
  .particle:nth-child(5) { left: 70%; }
  </style>
