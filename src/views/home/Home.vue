<template>
	<div id="home">
    <nav-bar class="home-nav">
      <template v-slot:center>
        <span>购物街</span>
      </template>
    </nav-bar>
  </div>
</template>

<script>
  import NavBar from "components/common/navbar/NavBar";
  export default {
    name: "Home",
    components: {NavBar}
  }
</script>

<style scoped>

.home-nav{
  background-color: var(--color-tint);
  color: #fff;
}

</style>
