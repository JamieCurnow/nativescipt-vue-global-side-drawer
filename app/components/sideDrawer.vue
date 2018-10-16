<template lang="html">
  <RadSideDrawer ref="drawer" drawerLocation="Left" :gesturesEnabled="gesturesEnabled">
    <StackLayout ~drawerContent backgroundColor="#ffffff">
      <slot name="drawerContent"></slot>
    </StackLayout>
    <Frame ~mainContent>
      <slot name="mainContent"></slot>
    </Frame>
  </RadSideDrawer>
</template>

<script>
import sideDrawer from '~/mixins/sideDrawer'
export default {
  mixins: [sideDrawer]
}
</script>

<style lang="css">
</style>
