<template>
  <div class="nav" id="nav">
    <div class="nav-label" id="nav-label">
      <h1 class="nav-logo">CesInternship</h1>
      <nuxt-link to="/">Accueil</nuxt-link>
      <nuxt-link to="/about">Offres</nuxt-link>
      <nuxt-link to="/contact">Contacts</nuxt-link>
      <button @click="responsive" href="#" class="icon">
        <i class="fa fa-bars fa-2x"></i>
      </button>
    </div>
    <div class="nav-button">
     <nuxt-link to="/about"> <button >Connexion</button></nuxt-link>
    </div>
  </div>
</template>

<style lang="scss">
    @import "assets/style/app.scss";
    @import "assets/style/navbar.scss";
</style>


<script>


export default {
  methods: {
    responsive: function () {
      console.log("Ouverture");
      let nav = document.getElementById("nav");
      if (nav.className == "nav") {
        nav.className += "responsive";
      }else{
        nav.className = "nav";
        
      }
    }
  }
}
</script>
