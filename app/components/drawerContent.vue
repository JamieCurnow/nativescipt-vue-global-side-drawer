<template lang="html">
  <ScrollView>
    <StackLayout width="100%">
      <Label class="drawer-header" text="Drawer"/>

      <Label
        v-for="(page, i) in pages"
        @tap="goToPage(page.component)"
        class="drawer-item"
        :text="page.name"
        :key="i"
      />

      <Button class="drawer-close-button" @tap="closeDrawer()">Close Drawer</Button>
    </StackLayout>
  </ScrollView>
</template>

<script>
import sideDrawer from '~/mixins/sideDrawer'
export default {
  mixins: [sideDrawer],
  data () {
    return {
      // define our pages, making sure the component matches that defined in /app/router/index.js
      pages: [
        { name: 'Home', component: this.$routes.Home },
        { name: 'Page One', component: this.$routes.PageOne },
        { name: 'Page Two', component: this.$routes.PageTwo }
      ]
    }
  },
  methods: {
    goToPage (pageComponent) {
      // use the manual navigation method
      this.$navigateTo(pageComponent)
      // and we probably want to close the drawer when changing pages
      this.closeDrawer()
    }
  }
}
</script>

<style lang="css">
</style>
