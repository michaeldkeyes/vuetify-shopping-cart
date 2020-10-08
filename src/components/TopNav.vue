<template>
  <div>
    <v-app-bar>
      <v-toolbar-title>Awesome Shop</v-toolbar-title>

      <v-spacer></v-spacer>

      <span class="hidden-sm-and-up">
        <v-btn @click.stop="drawer = !drawer"> Menu </v-btn>
      </span>

      <v-toolbar-items class="hidden-xs-only">
        <v-btn :to="{ name: 'Home' }" exact text>
          <v-icon small left>fa-home</v-icon>
          Home
        </v-btn>
        <v-btn :to="{ name: 'Store' }" text>
          <v-icon small left>fa-shopping-basket</v-icon>
          Store
        </v-btn>
        <v-btn :to="{ name: 'Cart' }" text>
          <v-icon small left>fa-shopping-cart</v-icon>
          Cart
        </v-btn>
      </v-toolbar-items>
    </v-app-bar>
    <v-navigation-drawer v-model="drawer" absolute temporary right>
      <v-list>
        <v-list-item
          v-for="item in items"
          :key="item.title"
          :to="{ name: item.link }"
          link
          exact
        >
          <v-list-item-icon>
            <v-icon small>fa-{{ item.icon }}</v-icon>
          </v-list-item-icon>
          <v-list-item-content>
            <v-list-item-title> {{ item.title }}</v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
  </div>
</template>

<script>
export default {
  name: "TopNav",
  data() {
    return {
      drawer: false,
      items: [
        { title: "Home", link: "Home", icon: "home" },
        { title: "Store", link: "Store", icon: "shopping-basket" },
        { title: "Cart", link: "Cart", icon: "shopping-cart" },
      ],
    };
  },
};
</script>
