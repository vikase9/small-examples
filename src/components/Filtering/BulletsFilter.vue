<template>
  <div>
    <div
      class="
        flex
        justify-around
        items-center
        bg-pink-500
        py-3
        text-white
        font-bold
        text-lg
      "
    >
      <label class="cursor-pointer"
        ><input type="radio" v-model="selectedCategory" value="All" />
        All</label
      >
      <label class="cursor-pointer"
        ><input type="radio" v-model="selectedCategory" value="Cricketers" />
        Cricketers</label
      >
      <label class="cursor-pointer"
        ><input type="radio" v-model="selectedCategory" value="Actors" />
        Actors</label
      >
      <label class="cursor-pointer"
        ><input type="radio" v-model="selectedCategory" value="Singers" />
        Singers</label
      >
    </div>

    <ul class="flex items-center flex-col mt-16">
      <li class="pb-9" v-for="role in filteredRole" :key="role.name">
        <span class="bg-yellow-400 p-3 font-serif font-bold">{{
          role.name
        }}</span>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      role: [
        { name: "Sachin Tendulkar", category: "Cricketers" },
        { name: "Yuvraj Singh", category: "Cricketers" },
        { name: "Virat Kohli", category: "Cricketers" },
        { name: "Yash", category: "Actors" },
        { name: "Hrithik Roshan", category: "Actors" },
        { name: "Madhuri Dixit", category: "Actors" },
        { name: "Lata Mangeshkar", category: "Singers" },
        { name: "Shreya Ghoshal", category: "Singers" },
        { name: "Arijit Singh", category: "Singers" },
      ],
      selectedCategory: "All",
    };
  },
  computed: {
    filteredRole() {
      var category = this.selectedCategory;

      if (category === "All") {
        return this.role;
      }
      return this.role.filter((item) => {
        return item.category === category;
      });
    },
  },
};
</script>
