<template>
  <div id="leftBar">
    <v-list>
      <v-list-item
        v-for="(item, i) in items"
        :key="i"
        :to="item.to"
        router
        exact
      >
        <v-list-item-action>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-item-action>
        <v-list-item-content>
          <v-list-item-title v-text="item.title" />
        </v-list-item-content>
      </v-list-item>
    </v-list>
  </div>
</template>
<script>
export default {
  name: "leftBar",

  mounted() {
    if(this.$auth.loggedIn){
      this.items.push({icon:'mdi-apps',title:'Profile',to:'/profile'})
    }
  },
  data() {
    return {
      items: [
        {
          icon: 'mdi-apps',
          title: 'Table',
          to: '/',
        },
      ],
    }
  },
}
</script>
