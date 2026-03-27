<script>
export default {
  name: 'App',
  data() {
    return {
      tab: this.$route.name,
      items: [
        { label: 'Domov', value: 'home', to: { name: 'home' } },
        { label: 'O nás', value: 'about', to: { name: 'about' } },
        { label: 'Produkty', value: 'products', to: { name: 'products' } },
        { label: 'Prehliadky', value: 'tours', to: { name: 'tours' } },
        { label: 'Kontakt', value: 'contact', to: { name: 'contact'} },
      ],
    }
  },
  watch: {
    $route(to) {
      this.tab = to.name
    },
  },
}
</script>

<template>
  <header>
  <div class="container">
    <v-card color="basil" class="main-card">
      <v-card-title class="text-center justify-center py-6">
        <img src="/img/madfoxLOGO.jpg" alt="MAdFOX Brewery" class="logo">
      <h1 class="font-weight-bold text-h2 text-basil">MAdFOX Brewery</h1>
      </img>
      
      </v-card-title>

      <v-tabs
        v-model="tab"
        color="basil"
        grow
      >
        <v-tab
          v-for="item in items"
          :key="item.label"
          :to="item.to"
          :value="item.value"
        >
          {{ item.label }}
        </v-tab>
      </v-tabs>

      <v-card color="basil" flat>
        <router-view />
      </v-card>
    </v-card>
  </div>
  </header>
</template>

<style scoped>
.main-card {
  width: auto;
  height: auto;
}
</style>