<template>
  <div class="about">
    <navbar/>
    <LoginForm />
  </div>
</template>


<script>

import LoginForm from '@/components/LoginForm.vue'
import Navbar from '../components/navbar.vue'

export default {
  name: 'About',
  components: {
    LoginForm,
    Navbar
  }
}
</script>
