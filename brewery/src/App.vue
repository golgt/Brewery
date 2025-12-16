<script setup>
import { ref, watch } from 'vue'
import { useRoute } from 'vue-router'

const route = useRoute()
const tab = ref(route.name)

const items = [
  { label: 'Domov', value: 'home', to: { name: 'home' } },
  { label: 'O nás', value: 'about', to: { name: 'about' } },
  { label: 'Produkty', value: 'products', to: { name: 'products' } },
  { label: 'Prehliadky', value: 'tours', to: { name: 'tours' } },
]

watch(
  () => route.name,
  (name) => {
    tab.value = name
  }
)
</script>

<template>
  <div class="container">
    <v-card color="basil">
      <v-card-title class="text-center justify-center py-6">
        <h1 class="font-weight-bold text-h2 text-basil">
          BASiL
        </h1>
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
</template>

