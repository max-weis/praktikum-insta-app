<template>
  <div id="app">
    <UebersichtBilder></UebersichtBilder>
    <NUtzerinfo></NUtzerinfo>
  </div>
</template>

<script>
import UebersichtBilder from './components/UebersichtBilder.vue'
import Nutzerinfo from '.componenrts/Nutzerinfo.vue'


export default {
  name: 'App',
  components: {
    UebersichtBilder,
    Nutzerinfo
  }
}
</script>

<style>

</style>
