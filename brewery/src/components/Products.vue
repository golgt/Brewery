<script>
import { useProductsStore } from '@/stores/counter'

export default {
  name: 'Products',
  props: {
    items: {
        type: Array,
        required: true,
    },
  },
  data() {
    return {
      productsStore: useProductsStore(),
      openIds: [],
    }
  },
  methods: {
    isOpen(id) {
      return this.openIds.includes(id)
    },
    toggle(id) {
      if (this.isOpen(id)) {
        this.openIds = this.openIds.filter(x => x !== id)
      } else {
        this.openIds.push(id)
      }
    },
    addItems(item) {
      this.productsStore.addItems(item)
    },
    removeItems(id) {
      this.productsStore.removeItems(id)
    },
  },
}
</script>

<template>
  <main class="products">

    <section>

      <v-container fluid>
        <v-row dense>
          <v-col
            v-for="item in items"
            :key="item.id"
            cols="12"
            md="6"
          >
            <v-card class="mx-auto" max-width="1000">
              <v-img
                height="200px"
                :src="item.src"
                cover
              ></v-img>

              <v-card-title>{{ item.name }}</v-card-title>

              <v-card-subtitle>
                {{ item.price.toFixed(2) }} €
              </v-card-subtitle>

              <v-card-actions>
                <v-btn
                  color="orange-lighten-2"
                  @click="addItems(item)"
                >
                  Pridať do košíka
                </v-btn>

                <v-spacer></v-spacer>

                <v-btn
                  :icon="isOpen(item.id) ? 'mdi-chevron-up' : 'mdi-chevron-down'"
                  @click="toggle(item.id)"
                ></v-btn>
              </v-card-actions>

              <v-expand-transition>
                <div v-show="isOpen(item.id)">
                  <v-divider></v-divider>

                  <v-card-text>
                    {{ item.description }}
                  </v-card-text>
                </div>
              </v-expand-transition>
            </v-card>
          </v-col>
        </v-row>
      </v-container>
    </section>

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
  </main>
</template>

<style scoped>
.products {
  display: grid;
  gap: 1.5rem;
}

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
