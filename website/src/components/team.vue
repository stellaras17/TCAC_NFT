<template>
  <div class="flex flex-center column">
      <h3 class="flex flex-center"> OUR TEAM </h3>
      <div class="div-style">

        

      <q-card class="my-card q-ma-sm div-row" flat bordered>
        <q-img
          src="../assets/RAFAELLA132.png"
          style="min-width:180px; min-height:180px"
        />

        <q-card-section>
          <div class="text-h3 q-mt-sm q-mb-xs">Rafaella</div>
          <div class="text-h5 text-grey">
            Artist
          </div>
        </q-card-section>

        <q-card-actions>

          <q-btn
            color="white"
            round
            flat
            dense
            :icon="expanded2 ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
            @click="expanded2 = !expanded2"
          />
        </q-card-actions>

        <q-slide-transition >
          <div v-if="expanded2">
            <q-separator />
            <q-card-section class="text-subitle2">
              {{ lorem2 }}
            </q-card-section>
          </div>
        </q-slide-transition>
      </q-card>

      <q-card class="my-card q-ma-sm div-row" flat >
        <q-img
          src="../assets/STELIOS31.png"
          style="min-width:180px; min-height:180px"
          
        />

        <q-card-section>
          <div class="text-h3 q-mt-sm q-mb-xs">Stelios</div>
          <div class="text-h5 text-grey">
            Developer
          </div>
        </q-card-section>

        <q-card-actions>

          <q-btn
            color="white"
            round
            flat
            dense
            :icon="expanded ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
            @click="expanded = !expanded"
          />
        </q-card-actions>

        <q-slide-transition>
          <div v-if="expanded">
            <q-separator />
            <q-card-section class="text-subitle2">
              {{ lorem }}
            </q-card-section>
          </div>
        </q-slide-transition>
      </q-card>

      <q-card class="my-card q-ma-sm div-row" flat bordered>
        <q-img
          src="../assets/ALEX113.png"
          style="min-width:180px; min-height:180px"
        />

        <q-card-section>
          <div class="text-h3 q-mt-sm q-mb-xs">Alex</div>
          <div class="text-h5 text-grey">
            Marketing
          </div>
        </q-card-section>

        <q-card-actions>

          <q-btn
            color="white"
            round
            flat
            dense
            :icon="expanded3 ? 'keyboard_arrow_up' : 'keyboard_arrow_down'"
            @click="expanded3 = !expanded3"
          />
        </q-card-actions>

        <q-slide-transition >
          <div v-if="expanded3">
            <q-separator />
            <q-card-section class="text-subitle2">
              {{ lorem3 }}
            </q-card-section>
          </div>
        </q-slide-transition>
      </q-card>
            
    </div>

    <h3>CORPORATE PARTNERS</h3>
    <div style="width: 80%; max-height: 180px">
      <div class="flex flex-center" >
        <div class="q-ma-lg">
          <img @click="goToURL('otp')" src="../assets/partners/OTP/horizontal.png" class="bg-white q-pa-md cursor-pointer" style="height: 130px; max-width: 450px;border-radius: 40px" alt="">
           <q-tooltip class="bg-positive text-weight-bold text-h6 text-black" transition-show="scale" transition-hide="scale" v-model="showing">One Tree Planted</q-tooltip>
        </div>

        <div class="q-ma-lg">
          <img @click="goToURL('ss')" src="../assets/partners/Surge/SSLOGO.png" class="bg-white q-pa-md cursor-pointer" style="height: 130px; max-width: 150px; border-radius: 40px;" alt=""/>
          <q-tooltip class="bg-positive text-weight-bold text-h6 text-black" transition-show="scale" transition-hide="scale" v-model="showing2">Surge Sanctuary</q-tooltip>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from 'vue'
import { openURL } from 'quasar'

export default {
  setup () {
    return {
      expanded: ref(false),
      expanded2: ref(false),
      expanded3: ref(false),
      showing: ref(false),
      showing2: ref(false),
      lorem: 'Stelios is a developer with a BSc in Computer Science. He has previously worked in web 3.0 applications and server developing.',
      lorem2: 'Rafaella is an artist with a BA in product design. She has previously worked on various fine art and digital art projects.',
      lorem3: 'Alex is a marketing strategist with years of experience in the industry. He has helped numerous projects and communities grow in the past.'
    }
  },
  methods: {
    goToURL(url) {
      switch(url){
        case 'otp':
          openURL('https://onetreeplanted.org/')
        case 'ss':
          openURL('https://www.surgesanctuary.org/')
      }
      
    }
  }
}
</script>

<style lang="scss" scoped>
  h3{
  color: black;
  font-family: "Lucida Console";
  font-weight: 900;
  text-decoration-line: underline;
  text-decoration-thickness: 10px;
  transition: 0.3 ease text-decoration;
  }

.q-icon{
  color: white !important;
}
.my-card{
  width: 100%;
  min-width: 400px;
  max-width: 400px;
} 
.div-row{
  display: inline-block;

}
.div-style{
  margin: 0 auto;
}

.text-h3{
  color: white;
  font-family: "Lucida Console";
  font-weight: 900;
}
.text-h5{
  font-family: "Lucida Console";
  font-weight: 900;
}
.text-subitle2{
  color: white;
  font-family: "Lucida Console";
  font-weight: 900;
}
.q-card{
  background-color: black;
}

.tooltip {
  position: relative;
  display: inline-block;
  border-bottom: 1px dotted black;
}

.tooltip .tooltiptext {
  visibility: hidden;
  width: 120px;
  background-color: black;
  color: #fff;
  text-align: center;
  border-radius: 6px;
  padding: 5px 0;

  /* Position the tooltip */
  position: absolute;
  z-index: 1;
}

.tooltip:hover .tooltiptext {
  visibility: visible;
}


@media screen and (max-width: 768px){
  .my-card{  
    width: 100%;
    min-width: 180px !important;
    max-width: 180px !important;
    min-height: 340px !important;
    max-height: 340px !important
  } 

  .q-btn{
    display: none !important;
  }

  .text-h3{
    font-size: 32px;
    color: white;
    font-family: "Lucida Console";
    font-weight: 900;
  }
  .text-h5{
    font-size: 18px;
    font-family: "Lucida Console";
    font-weight: 900;
  }

}


</style>