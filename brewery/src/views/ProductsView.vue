<script>
  import CtaBanner from '@/components/CtaBanner.vue';
  import Footer from '@/components/Footer.vue';

  export default{
    name: 'ProductView',
    components: {
      CtaBanner,
      Footer,
    }
  }
</script>

<template>
  
  <h1>Stránka s produktami</h1>


  <footer>
    <CtaBanner
      heading="Navštívte náš pivovar už tento víkend"
      body="Prehliadka, degustácia a čas s našimi sládkami. Rezervujte si termín online a my sa postaráme o zvyšok."
      :action="{ label: 'Rezervovať', to: { name: 'tours' } }"
    />
    <Footer/> 
  </footer>
  
</template>

<style>
  @media (min-width: 1024px) {
    .about {
      min-height: 100vh;
      display: flex;
      align-items: center;
    }
  }
  </style>
  
