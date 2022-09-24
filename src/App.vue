
<template>
  <div id="app" class="appp">

    <Menu />

    <div class="conten ">
      <router-view />
    </div>




  </div>

</template>

<script>
import Menu from './components/Menu';

export default {
  name: 'App',
  data: () => ({

  }),
  components: {
    Menu
  }
}
</script>

<style lang="scss">
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;

}

.appp {
  display: flex;


  .conten {
    flex: 1 1 0;
    padding-left: 4rem;

    @media(max-width: 768px) {
      padding-left: 6rem;
    }
  }
}
</style>