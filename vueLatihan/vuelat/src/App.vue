<template>
  <div id="app">
<Header v-on:ganti-hero="gantiHero"></Header>

    <main>
       <Hero v-bind:hero="hero"></Hero> 
    </main>

<Footer></Footer>

  </div>
</template>

<script>
import Header from './components/Header.vue'
import Footer from './components/Footer.vue'
import Hero from './components/Hero.vue'

export default {
  components: {
     Header,
     Footer,
     Hero
  },
    name: 'app',
    data: function(){
        return{
            hero:{
                nama: 'Freya',
                type: 'Fighter',
                gambar: 'freya.jpg'
            }
        }
    }, 
    methods: {
          gantiHero: function(){
            this.hero.nama ='Zhask',
            this.hero.type ='Mage',
            this.hero.gambar ='zhask.jpeg'
          }
        },
    computed:{
        gambar: function() {
            return require('./assets/hero/' +this.hero.gambar)
        }
    }

}
</script>

<style>
#app {
    font-family: 'aventir', Helvetica, Arial, sans-serif;
    -webkit-font-smooting: antialiased;
    -moz-osx-font-smooting: grayscale;
    color:#2c3e50;
    margin-top: 60px;
    }
</style>