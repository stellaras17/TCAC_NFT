<template>
  <div>
      <h3 class="flex flex-center"> ROADMAP </h3>
      <div class="q-px-lg q-pb-md flex flex-center" style="margin:0 auto">
        <q-timeline layout="loose" color="accent">
          <q-timeline-entry heading>
            Minting
          </q-timeline-entry>

          <q-timeline-entry
            
            class="completed"
            icon="done"
            color="black">
            <div>
              <p class="heading">Before Mint</p>
              <q-list class="list-left">
                <p class="completed">floor price: 0.00 ETH.</p>
                <p>30% of the ETH collected from commissions will be used to help Ukraine.</p>
                <p>25 NFTs giveaway.</p>
                
              </q-list>
              
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            
            side="left"
            color="white"
          >
            <div>
              <p class="heading">2,500 minted</p>
              <q-list class="list-left">
                <p>floor price: 0.06 ETH.</p>
                <p>25 NFTs giveaway.</p>
                <p>12,500 total trees planted.</p>
                <p>12,500$ donated for animals.</p>
              </q-list>
              
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            tag="h3"
            color="white"
          >
            <div>
              <p class="heading">5,000 minted</p>
              <q-list class="list-right">
                <p>floor price: 0.08 ETH.</p>
                <p>Merch store opening.</p>
                <p>25 NFTs giveaway.</p>
                <p>37,500 total trees planted.</p>
                <p>37,500$ donated for animals.</p>
              </q-list>
            </div>
          </q-timeline-entry>
          <q-timeline-entry
            tag="h3"
            side="left"
            color="white"
          >
            <div>
              <p class="heading">7,500 minted</p>
              <q-list class="list-left" >
                <p>Floor price: 0.1 ETH.</p>
                <p>Merch giveaway to holders.</p>
                <p>25 NFTs giveaway.</p>
                <p>75,000 total trees planted.</p>
                <p>75,000$ donated for animals.</p>
              </q-list>
              
              
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            tag="h3"
            color="white"
          >
            <div>
              <p class="heading">10,000 minted</p>
              <q-list class="list-right" style="max-width:270px">
                <p>125,000 total trees planted.</p>
                <p>125,000$ donated for animals.</p>
                <p>Community voted giveaway.</p>
                <p>Add community's idea to merch.</p>
                <p>Gallery section is added to our website where all the avocados and their attributes are displayed.</p>
                <p>GMO substance released to the public to unlock the GMO Avocados NFT collection.</p>
                <p>Smart contract release.</p>
              </q-list>
	
            </div>
          </q-timeline-entry>

          <q-timeline-entry heading>
            Post-mint
          </q-timeline-entry>

          <q-timeline-entry
            side="left"
            color="white"
          >
            <div>
              <p class="heading">Environmental Contribution</p>
              <q-list class="list-left">
                <p>200,000 total trees planted.</p>
                <p>200,000$ total donated for animals.</p>
              </q-list>
            </div>
          </q-timeline-entry>

          <q-timeline-entry
            
            color="white"
          >
            <div>
              <p class="heading metaverse"><span class="">Metaverse</span></p>
              <q-list class="list-right" style="max-width:270px">
                <p>Our team develops game in the metaverse where players use their avocados to earn passive income.</p>
              </q-list>
	
            </div>
          </q-timeline-entry>

          
        </q-timeline>
    </div>
  </div>
</template>

<script>
export default {

}
</script>

<style scoped>
 h3{
  color: black;
  font-family: "Lucida Console";
  font-weight: 900;
  text-decoration-line: underline;
  text-decoration-thickness: 10px;
  transition: 0.3 ease text-decoration;
  }

div.q-px-lg {
  color: black;
  font-family: "Lucida Console";
  font-weight: 900 ;
  
}
.heading{
  font-size: 26px !important;
  line-height: 1 !important;
}

.list-right{
  margin-left:2.5%;
}
.list-left{
  margin-right:2.5%;
}
@media screen and (max-width: 768px){
  .metaverse{
    visibility: hidden;
  }
  .metaverse span::after {
    visibility: visible;
    content: ' Meta verse';
  }
}

</style>