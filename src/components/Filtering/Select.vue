<template>
  <div>
    <div class="flex justify-center mt-10">
      <select class="border-2 p-1" v-model="category">
        <option value="">All</option>
        <option value="Bike">Bike</option>
        <option value="Laptop">Laptop</option>
        <option value="Stationary">Stationary</option>
      </select>
    </div>
    <ul class="flex flex-col items-center mt-10">
      <li
        class="pb-8"
        v-for="product in filterProductsByCategory"
        :key="product.name"
      >
        <span class="bg-yellow-400 p-2 font-serif font-bold border-2 border-black">{{
          product.name
        }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      category: "",
      products: [
        { name: "Royal Enfield", category: "Bike" },
        { name: "Activa", category: "Bike" },
        { name: "Honda", category: "Bike" },
        { name: "Lenovo", category: "Laptop" },
        { name: "Dell", category: "Laptop" },
        { name: "Apple", category: "Laptop" },
        { name: "Text Books", category: "Stationary" },
        { name: "Pencil", category: "Stationary" },
        { name: "Eraser", category: "Stationary" },
      ],
    };
  },
  computed: {
    filterProductsByCategory(){
      return this.products.filter((product) => {
        return !product.category.indexOf(this.category);
      });
    },
  },
};
</script>
