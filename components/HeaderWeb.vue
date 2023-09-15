<template>
  <nav class="navbar navbar-expand bg-dark">
    <div class="container justify-content-between">
      <img src="../assets/TipWeb-Logo.png" alt="" style="height: 40px" />
      <ul class="nav nav-pills">
        <li class="nav-link">
          <NuxtLink class="text-light" to="/"> Beranda </NuxtLink>
        </li>
        <li class="nav-link">
          <NuxtLink class="text-light" to="./fintrack">
            FinTrack
          </NuxtLink>
        </li>
        <li class="nav-link">
          <NuxtLink class="text-light" to="./guide"> Guide</NuxtLink>
        </li>
        <li class="nav-link">
          <NuxtLink class="text-light" to="./src/testsb"> TestSB</NuxtLink>
        </li>
        <li class="nav-link">
          <NuxtLink class="text-light" to="./register"> Register</NuxtLink>
        </li>
      </ul>
    </div>
  </nav>
</template>
<script>
export default {}
</script>
