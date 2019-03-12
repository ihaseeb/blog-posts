<template>
  <v-navigation-drawer
    v-model="drawer"
    app
    dark
    temporary
  >
    <v-list>
      <v-list-tile
        v-for="link in links"
        :key='link.text'
        :to="link.to"
        :href="link.href"
        @click="onClick($event, link)"
      >
        <v-list-tile-title>{{link.text}}</v-list-tile-title>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>
</template>
<script>
import {
  mapGetters,
  mapMutations
} from 'vuex'
export default {
  computed: {
    ...mapGetters(['links']),
    drawer: {
      get () {
        return this.$store.state.drawer
      },
      set (val) {
        this.setDrawer(val)
      }
    }
  },
  methods: {
    ...mapMutations(['setDrawer']),
    onClick (e, item) {
      e.stopPropagation()
      if (item.to === '/') {
        this.$vuetify.goTo(0)
        this.setDrawer(false)
        return
      }
      if (item.to || !item.href) return
      this.$vuetify.goTo(item.href)
      this.setDrawer(false)
    }
  }
}
</script>
