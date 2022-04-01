<template>
  <div>
    <NavBar />
    <Nuxt />
    <FooterComponent />
  </div>
</template>

<script>
import NavBar from '../components/Shell/NavBar'
import FooterComponent from '../components/Shell/FooterComponent.vue'

export default {
    components: {
        NavBar,
        FooterComponent,
    }
}
</script>