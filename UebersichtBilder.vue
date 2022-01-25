<template>
  <div>
  <!-- Grid mit Bildern (3x3) -->
    <div class="row">
            <div v-for="bild in bilderUrl" :key="bild.media_url" class="col-xl-3 col-lg-4 col-md-6 mb-4">
                <div class="card" >
                    <img :src="bild" width="200px" height="200px">
                </div>
            </div>
        </div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  name: 'UebersichtBilder',
  props: {
    msg: String
  },
  data() {
    return {
      bilderUrl: [],
      newUrl: null
      }
  },
  mounted() {
    axios
      .get('https://graph.instagram.com/me/media?fields=media_url&access_token=xxxx') 
      .then((response) => {
        console.log(response.data.data)
        response.data.data.forEach(element => {
          console.log(element.media_url)
          this.bilderUrl.push(element.media_url)
        });
        })
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.card{
  width: 200px;
}
</style>
