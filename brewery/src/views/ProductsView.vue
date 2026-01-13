<script>
import CtaBanner from '@/components/CtaBanner.vue';
import Footer from '@/components/Footer.vue';
import Products from '@/components/Products.vue';

export default{
  name: 'ProductView',
  components: {
    CtaBanner,
    Footer,
    Products,

  },
  data() {
    return {
      productsForSale: [
        { id: 1, name: 'MAdFOX Brewery IPA', price: 0.5, src: '/img/ipa.jpg', description: 'Výrazná India Pale Ale s bohatou chmeľovou arómou citrusov a tropického ovocia. Príjemná horkosť je vyvážená plným telom a sviežim dozvukom, ktorý ocenia milovníci moderných craft pív.' },
        { id: 2, name: 'MAdFOX Brewery Radler', price: 1.0, src: '/img/radler.jpg', description: 'Osviežujúca kombinácia ľahkého piva a prírodnej citrusovej limonády. Ideálny spoločník na horúce dni, ktorý ponúka nízky obsah alkoholu a dokonale vyváženú sladko-kyslú chuť.' },
        { id: 3, name: 'MAdFOX Brewery Stout', price: 2.5, src: '/img/stout.jpg', description: 'Tmavé pivo s plnou, zamatovou textúrou a tónmi praženej kávy, horkej čokolády a jemného karamelu. Bohatá chuť a dlhý dozvuk robia zo stouta ideálnu voľbu pre pomalé vychutnávanie.' },
        { id: 4, name: 'MAdFOX Brewery Lager', price: 0.9, src: '/img/lager.jpg', description: 'Klasický spodne kvasený ležiak s čistou, vyváženou chuťou a jemnou chmeľovou horkosťou. Ľahko piteľný, osviežujúci a vhodný na každú príležitosť.' },
        { id: 5, name: 'MAdFOX Brewery Sour', price: 3.2, src: '/img/sour.jpg', description: 'Odvážne kyslé pivo s ovocnými tónmi a sviežou aciditou. Ľahké telo a netradičný chuťový profil z neho robia ideálnu voľbu pre tých, ktorí radi objavujú nové pivné zážitky.' },
        { id: 6, name: 'MAdFOX Brewery Radler 0.0%', price: 0.5, src: '/img/radler00.jpg', description: 'Moderný nealkoholický radler s osviežujúcou citrusovou chuťou a dokonale vyváženou sladko-kyslou harmóniou. Ideálna voľba pre každého, kto si chce vychutnať plnú chuť radlera bez alkoholu – kedykoľvek a bez kompromisov.' },
      ],
    }
  },
}

</script>

<template>
  <main>
    <h1>Produkty</h1>
    <h2 class="section-title">Ponuka</h2>
    <Products :items="productsForSale" />

    <footer>
      <CtaBanner
        heading="Navštívte náš pivovar už tento víkend"
        body="Prehliadka, degustácia a čas s našimi sládkami. Rezervujte si termín online a my sa postaráme o zvyšok."
        :action="{ label: 'Rezervovať', to: { name: 'tours' } }"
      />
      <Footer/> 
    </footer>
  </main>
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
  
