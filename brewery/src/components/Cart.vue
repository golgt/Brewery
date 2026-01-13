<script>
import { useProductsStore } from '@/stores/counter'

export default {
  name: 'Cart',
  data() {
    return {
      productsStore: useProductsStore(),
    }
  },
  methods: {
    removeItems(id) {
      this.productsStore.removeItems(id)
    },
  },
}
</script>

<template>
  <section class="cart-section">
    <h2 class="section-title">Košík</h2>

    <div v-if="productsStore.cartItems.length === 0" class="empty">Košík je prázdny.</div>

    <v-card v-else class="mx-auto" max-width="800">
      <v-list>
        <v-list-item
          v-for="item in productsStore.sortItems"
          :key="item.id"
        >
          <v-list-item-title>{{ item.name }}</v-list-item-title>
          <v-list-item-subtitle>
            {{ item.price.toFixed(2) }} €
          </v-list-item-subtitle>

          <template #append>
            <v-btn
              color="error"
              variant="text"
              @click="removeItems(item.id)"
            >
              Odstrániť
            </v-btn>
          </template>
        </v-list-item>
      </v-list>
    </v-card>
  </section>
</template>

<style scoped>
.section-title {
  margin: 0 0 0.5rem;
  font-size: 1.25rem;
  font-weight: 700;
}

.empty {
  color: #555;
  font-style: italic;
}

.cart-section {
  margin-top: 2rem;
}
</style>
