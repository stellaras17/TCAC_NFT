<template>
  <div style="width: 100%">
    <h3 class="flex flex-center"> FAQ </h3>
  
    <div class="q-pa-md center-div" style="width: 100%; margin:0 auto; max-width: 1098px">
      <q-list bordered style="width: 100%;
            font-family: 'Lucida Console';
            font-weight: 900;" class=" bg-positive rounded-borders q-mb-lg">

        <q-expansion-item
          expand-separator
          label="How do I get an Avocado?">
          <q-card>
            <q-card-section style="color: black">
              Install Metamask on your chrome browser and fund it from an exchange like Binance and Coinbase. Then click the MINT button and complete the transaction. After minting, your avocado should be visible on opensea.
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          label="How do I get whitelisted?">
          <q-card>
            <q-card-section style="color: black">
              First 75 people to reach level 30 or have 3+ invites in our discord server will be whitelisted. The rest 25 positions will be filled via our first giveaway.
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          label="How many TCAC NFTs are available?"
        >
          <q-card>
            <q-card-section style="color: black">
              There are 10000 unique NFTs which can be minted from our official website. Once all of them are minted, you can buy from other holders via opensea. 
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          label="Is TCAC a good investment?"
        >
          <q-card>
            <q-card-section style="color: black">
              TCAC minting was designed to award early investors, for each 25% that is minted off the total supply, the floor price rises by 0.02 ETH. By minting a TCAC you also contribute to the benefit of the environment by planting trees and saving animals. In addition, our team has set ambitious goals for the future of the project which can be viewed in the roadmap channel. 
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          label="Are the cards rare?"
        >
          <q-card>
            <q-card-section style="color: black">
              Yes! Each avocado has 8 components, there are 10,000 NFTs out of 24,570,000 possible combinations. In addition to that only 20 super rare avocados have the gem pit. The rarity of each component can be seen on opensea after the official reveal.
            </q-card-section>
          </q-card>
        </q-expansion-item>

        <q-expansion-item
          expand-separator
          label="Is there any commission for selling a TCAC?"
        >
          <q-card>
            <q-card-section style="color: black">
              Our team collects 1% of each TCAC for the project's further developments.
            </q-card-section>
          </q-card>
        </q-expansion-item>
      </q-list>
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
  .center-div{
    display: flex;
    justify-content: center;
  }
  .q-item__label{
    color: #e8ffa7;
    font-family: "Lucida Console";
    font-weight: 900;
  }
  .q-card__section{
    background-color: #FFFFA7;
  }

</style>