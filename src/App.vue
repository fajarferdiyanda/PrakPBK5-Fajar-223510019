<template>
  <div>
    <Navbar />
    <div class="container mt-4">
      <Carousel />
      <div class="card-container mt-4">
        <Card 
          v-for="product in products" 
          :key="product.id" 
          :title="product.name" 
          :description="product.description" 
          :url="product.url" 
        />
      </div>
    </div>
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import Carousel from './components/Carousel.vue';
import Card from './components/Card.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    Carousel,
    Card,
    Footer
  },
  data() {
    return {
      products: [
        { 
          id: 1, 
          name: 'Nike Dunk Low Shoes', 
          description: '$180.00.', 
          url: 'https://static.nike.com/a/images/q_auto:eco/t_product_v1/f_auto/dpr_1.5/h_383,c_limit/bded6725-dc92-4e77-881f-d784ffde77e2/dunk-low-shoes-wbxcmN.png' 
        },
        { 
          id: 2, 
          name: 'Air Jordan 1 Low Shoes', 
          description: '$160', 
          url: 'https://static.nike.com/a/images/q_auto:eco/t_product_v1/f_auto/dpr_1.5/h_383,c_limit/4693a962-0ea1-4677-b5fd-eeed550ab4d3/air-jordan-1-low-shoes-zTWr01.png' 
        },
        { 
          id: 3, 
          name: 'Nike Dunk Low Retro', 
          description: '$180.00', 
          url: 'https://static.nike.com/a/images/q_auto:eco/t_product_v1/f_auto/dpr_1.5/h_383,c_limit/a3e7dead-1ad2-4c40-996d-93ebc9df0fca/dunk-low-retro-shoe-66RGqF.png' 
        },
        { 
          id: 4, 
          name: 'Nike Dunk Low', 
          description: '$180.00', 
          url: 'https://static.nike.com/a/images/t_PDP_864_v1,f_auto,q_auto:eco/4eae23a9-b240-4a53-98c7-d5502fe3f7dc/dunk-low-shoes-B6FZNV.png' 
        },
        { 
          id: 5, 
          name: 'Nike Air Max Pulse', 
          description: '$161.99', 
          url: 'https://static.nike.com/a/images/c_limit,w_592,f_auto/t_product_v1/858f1aa8-bfa9-4536-99bd-c566a64c7665/air-max-pulse-shoes-H9PCsD.png' 
        },
        { 
          id: 6, 
          name: 'Nike air Max Dn', 
          description: 'A$230', 
          url: 'https://static.nike.com/a/images/q_auto:eco/t_product_v1/f_auto/dpr_1.5/h_381,c_limit/cc87d541-1023-4c86-bd45-d6d3dc9e6cfd/air-max-dn-shoes-q51Wwn.png' 
        }
      ]
    };
  }
};
</script>

<style>
body {
  background-color: rgb(159, 199, 210);
}

.card-container {
  display: flex;
  justify-content: space-between;
  flex-wrap: wrap;
  gap: 16px; /* Optional: Adjust the space between cards */
}

.card {
  flex-basis: calc(33.33% - 16px); /* Atur lebar kartu dengan ketiga bagian dari wadah dikurangi jarak antar kartu */
}
</style>
