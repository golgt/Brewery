<script>
  import About from '@/components/About.vue';
  import CtaBanner from '@/components/CtaBanner.vue';
  import Footer from '@/components/Footer.vue';
  import Team from '@/components/Team.vue';

  export default{
    name: 'AboutView',
    components: {
      CtaBanner,
      Footer,
      About,
      Team,
    },
    data(){
      return{
        cards:[
        { title: 'Marián Full', subtitle: 'Pivovarník', src: '/Brewery/img/pivovarnik.jpg', flex: 12 },
        { title: 'Petra Nováková', subtitle: 'PR', src: '/Brewery/img/pr.jpg', flex: 4 },
        { title: 'Tomáš Kováč', subtitle: 'Pivný someliér', src: '/Brewery/img/somelier.jpg', flex: 4 },
        { title: 'Lucia Horváthová', subtitle: 'Vedúca výroby', src: 'Brewery/img/somelier.jpg', flex: 4 },
        { title: 'Martin Blaško', subtitle: 'Technik', src: '/Brewery/img/technik.jpg', flex: 4 },
        { title: 'Zuzana Šimková', subtitle: 'Kontrola kvality', src: '/Brewery/img/kontrola.jpg', flex: 4 },
        { title: 'Karol Krabiva', subtitle: 'Obchod', src: '/Brewery/img/obchodnik.jpg', flex: 4 },
        ],
      }
    }
  }
  
</script>

<template>

  <About/>
  <Team :cards="cards"/>

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
.about {
  display: grid;
  gap: 1.5rem;
}
</style>