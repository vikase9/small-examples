<template>
  <div>
    <div class="flex justify-around bg-black py-3 text-white">
      <nav class="navbar-container" v-for="item in menuItems" :key="item.name">
        <div @mouseover="handleOver(e, item.name)">
          <router-link :to="item.to">{{ item.name }}</router-link>
        </div>
      </nav>
    </div>
    <div
      v-if="show"
      class="show text-white float-right mr-36 py-2 px-3 bg-black"
    >
      <h4>{{ dropdown }}</h4>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DropDownHover',
  data() {
    return {
      show: false,
      menuItems: [
        {
          name: 'Home',
          to: '/',
        },
        {
          name: 'History',
          to: '/our-history',
        },
        {
          name: 'About',
          to: '/about',
          children: [
            {
              name: 'Contact Info',
              to: '/contact',
            },
            {
              name: 'Cat',
              to: '/contact',
            },
          ],
        },
      ],
    };
  },
  methods: {
    handleOver(e, data) {
      if (data == 'About') {
        this.show = !this.show;
      } else {
        this.show = false;
      }
    },
  },
  computed: {
    dropdown() {
      const res = this.menuItems[2].children;
      const final = res.map((item) => {
        return item.name;
      });
      const exists = final;
      return exists;
    },
  },
};
</script>
