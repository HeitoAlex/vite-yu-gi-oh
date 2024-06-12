<script>
import AppHeader from "./components/AppHeader.vue";
import AppMain from "./components/AppMain.vue";

export default {
  data(){
    return{

    }
  },
  components: {
    AppHeader,
    AppMain
  }
}
</script>

<template>
  <AppHeader/>
  <AppMain/>
</template>

<style lang="scss">
  @use './styles/partials/mixins';
  @use './styles/partials/variables';
  @use './styles/general.scss';
  @use '../node_modules/bootstrap/scss/bootstrap.scss';

</style>
