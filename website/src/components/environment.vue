<template>
  <div style="width: 100%">
      <h3 class="flex flex-center"> ENVIRONMENT </h3>
      <div class="" style="width:55%; margin: 0 auto">
        <q-carousel
          v-model="slide"
          transition-prev="scale"
          transition-next="scale"
          swipeable
          animated
          control-color="black"
          control-type="push"
          navigation
          padding
          arrows
          height="400px"
          class="text-white shadow-1 rounded-borders"
        >

          <q-carousel-slide  name="slide1" class="column no-wrap flex-center">
            <h4 style="text-align: center">2,500 - 5,000 MINTED</h4>
            <div class="row flex felx-center" style="display: inline-block, flex !important; width: 50%">
              <div class="column" style="display: flex; justify-content: center;" >
                <q-icon color="black" name="fas fa-tree" size="46px" style="margin: 0 auto" />
                <div class="q-mt-md text-center">
                  10 PLANTED PER MINT
                </div>
              </div>
              <q-space />
              <div class="column" style="display: flex; justify-content: center;" >
                <q-icon color="black" name="fas fa-dog" size="46px" style="margin: 0 auto" />
                <div class="q-mt-md text-center ">
                  10$ DONATED PER MINT
                </div>
              </div>
            </div>
          </q-carousel-slide>

          <q-carousel-slide  name="slide2" class="column no-wrap flex-center">
            <h4 style="text-align: center">5,000 - 7,500 MINTED</h4>
            <div class="row flex felx-center" style="display: inline-block, flex !important; width: 50%">
              <div class="column" style="display: flex; justify-content: center;" >
                <q-icon color="black" name="fas fa-tree" size="46px" style="margin: 0 auto" />
                <div class="q-mt-md text-center">
                  15 PLANTED PER MINT
                </div>
              </div>
              <q-space />
              <div class="column" style="display: flex; justify-content: center;" >
                <q-icon color="black" name="fas fa-dog" size="46px" style="margin: 0 auto" />
                <div class="q-mt-md text-center">
                  15$ DONATED PER MINT
                </div>
              </div>
            </div>
          </q-carousel-slide>

          <q-carousel-slide  name="slide3" class="column no-wrap flex-center">
            <h4 style="text-align: center">7,500 - 10,000 MINTED</h4>
            <div class="row flex felx-center" style="display: inline-block, flex !important; width: 50%">
              <div class="column" style="display: flex; justify-content: center;" >
                <q-icon color="black" name="fas fa-tree" size="46px" style="margin: 0 auto" />
                <div class="q-mt-md text-center">
                  20 PLANTED PER MINT
                </div>
              </div>
              <q-space />
              <div class="column" style="display: flex; justify-content: center;" >
                <q-icon color="black" name="fas fa-dog" size="46px" style="margin: 0 auto" />
                <div class="q-mt-md text-center">
                  20$ DONATED PER MINT
                </div>
              </div>
            </div>
          </q-carousel-slide>
      
        </q-carousel>
      </div>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    return {
      slide: ref('slide1'),
      lorem: 'Lorem ipsum dolor, sit amet consectetur adipisicing elit. Itaque voluptatem totam, architecto cupiditate officia rerum, error dignissimos praesentium libero ab nemo.'
    }
  }
}
</script>

<style lang="scss" scoped>
h4{
  color: black;
  font-size: 52px;
  font-family: "Bahnschrift SemiBold";
  font-weight: 800;
  letter-spacing: 5px;
  
}
.q-mt-md{
  color: black;
  font-size: 14px;
  font-family: "Bahnschrift SemiBold";
 // font-family: "Lucida Console";
  font-weight: 900;
}
h3{
color: black;
font-family: "Lucida Console";
font-weight: 900;
text-decoration-line: underline;
text-decoration-thickness: 10px;
transition: 0.3 ease text-decoration;
}

.q-carousel {
  background-image: url('../assets/sea2.jpg');
  background-size: cover;
}

@media screen and (max-width: 768px){
h4{
  color: black;
  font-size: 22px;
  letter-spacing: normal;
  font-weight: 900;
}
.q-mt-md{
  color: black;
  font-size: 10px;
 // font-family: "Lucida Console";
  font-weight: 900;
}

}
</style>