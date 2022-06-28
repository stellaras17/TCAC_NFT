<template>
  <div>
      <div class="flex flex-center column">
        
        <q-parallax :height="800">
          <template v-slot:media>
            
            <img src="../assets/banner.jpg">
            
          </template>

          <template v-slot:content="scope">
            
            <div
              class=" column items-center"
              :style="{
                //opacity: 0.45 + (1 - scope.percentScrolled) * 0.55,
                top: (scope.percentScrolled * 60) + '%',
                left: 0,
                right: 0
              }"
              style="height: 100%"
            >
              <h3  style="fixed-top !important; font-size:54px; text-align:center; opacity: 1 !important"> Welcome to The Crazy Avocado Club </h3>

                <div v-if="!connected" class="flex flex-center column" style="width:100%">
                  <div class="text-h4 text-black text-center">Connect your MetaMask to start minting!</div>
                  <div class="column q-mt-lg" style="width:30%">
                        
                    <q-btn @click="doWeb3Shit" style="font-family: 'Lucida Console' !important;
                        font-weight: 900;" :ripple="false" width="258px" size="38px" color="black" text-color="white" label="CONNECT">
                        <q-tooltip class="bg-accent">Minting starts on Feb 26!</q-tooltip>
                    </q-btn>
                  </div>
                </div>

                <div v-else class="flex flex-center column" style="width:100%">
                  <h5> {{10000-supply}}/10000</h5>
                  <div class="bg-positive" style="border-radius: 20px">
                  <q-item >
                    <q-item-section side>
                      <q-avatar color="green" size="28px">
                      </q-avatar>
                    </q-item-section>
                    <q-item-section>
                      <q-item-label style="color: black; font-family: 'Lucida Console';
                          font-weight: bold">{{account}}</q-item-label>
                    </q-item-section>
                  </q-item>
                  </div>
                  <div class="column q-mt-lg" style="width:30%">
                        
                    <q-btn @click="mint" class="q-mb-lg" style="font-family: 'Lucida Console' !important;
                        font-weight: 900;" :ripple="false" width="258px" size="38px" color="black" text-color="white" label="MINT">
                        <q-tooltip class="bg-accent">Minting starts on Feb 26!</q-tooltip>
                    </q-btn>

                    <h5 class="flex flex-center">{{ cost * amount }} ETH</h5>
                        
                    <q-slider
                      class="q-mt-md"
                      v-model="amount"
                      track-size="22px"
                      thumb-size="38px"
                      marker-labels
                      :min="1"
                      :max="5"
                    />
                </div>
              </div>
                
            </div>
          </template>
        </q-parallax>
              
      </div>
  </div>
</template>

<script>
import { ethers } from "ethers";
import abi from '../assets/abi.json'
import { parseBytes32String } from '@ethersproject/strings';
var contract

export default {
  data() {
    return {
      amount: 1,
      options: [1,2,3,4,5],
      contractAddress: '0x861E99329cd05Dcff865141D8947b88d8271e909',
      connected: false,
      account: '',
      supply: 0,
      cost: 0
    }
  },
  methods:{
    mint() {
      this.doWeb3Shit()
      this.getSupply()    
      this.safemint()
    },
    doWeb3Shit() {
      try {
        if(window.ethereum){
          window.ethereum.request({method: 'eth_requestAccounts'})
          .then(result => {
            this.account = result[0]
            this.connected = 'true'
          })
        } else {
          alert('You need metamask')
          return
        }
        let provider = new ethers.providers.Web3Provider(window.ethereum);
        let signer = provider.getSigner();
        contract = new ethers.Contract(this.contractAddress, abi, signer);
        this.getSupply()
        this.getPrice()
      }
      catch(error) { alert(error) }
    },
    async getSupply() {
      try {
        let val = await contract.functions.totalSupply();
        let hex = val[0]
        hex = hex[Object.keys(hex)[0]]
        this.supply = parseInt(hex,16);
      }
      catch(err){
        console.log(err);
      }
      },
    async getPrice() {
      let cost = await contract.functions.checkCost(this.supply);
      cost = cost[0]
      cost = cost[Object.keys(cost)[0]]
      cost = parseInt(cost,16);
      let price = this.amount * cost;
      price=price/1000000000000000000;
      price = price.toString();
      this.cost = price
      console.log(this.cost);
    },
    async safemint() {
        let cost = await contract.functions.checkCost(this.supply);
        cost = cost[0]
        cost = cost[Object.keys(cost)[0]]
        cost = parseInt(cost,16);
        let price = this.amount * cost;
        price=price/1000000000000000000;
        price = price.toString();
        this.cost = price
        const options = {value: ethers.utils.parseEther(price)}
        contract.mint(this.amount, options).catch(e => {
          if (e.code === 4001){
            alert('User denied Transaction')
          }
          if (e.error.code === -32603){
            alert('Cannot own more than 5 avocados!')
          }
        });
    }
  },
}
</script>

<style scoped >
.q-slider{
  font-size: 24px !important;
  font-family: "Lucida Console";
  font-weight: 900;
}
h3{
  color: black;
  font-family: "Lucida Console";
  line-height: 1.3;
  font-weight: 900;
  text-decoration-line: underline;
  text-decoration-thickness: 10px;
  transition: 0.3 ease text-decoration;
}
h5{
  color: black;
  font-family: "Lucida Console";
  line-height: 1.3;
  font-weight: 900;
  font-size: 64px;
  margin: 0;
  margin-bottom: 10px;
}
.text-h4{
  color: black;
  font-family: "Lucida Console";
  font-weight: 900;

}
p{
  color: #FFFFA7;
  font-family: "Lucida Console";
}
  span.block  {
  color: black;
  font-family: "Lucida Console" !important;
  font-weight: 900;
}
</style>