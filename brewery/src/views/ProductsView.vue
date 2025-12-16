<script setup>
  import Products from '../components/Products.vue'
  
  </script>
  
  <template>
    <main>
      <Products/>
    </main>
  </template>
  
  <style>
    @media (min-width: 1024px) {
      .products {
        min-height: 100vh;
        display: flex;
        align-items: center;
      }
    }
  </style>