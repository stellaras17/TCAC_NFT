<template>
    <q-page class="flex flex-center">

   <q-header bordered class="bg-white text-white" height-hint="98">
      <q-toolbar style="min-height: 55px;" >
        <q-toolbar-title class="text-primary">
          <q-avatar color="primary">
            <img src="../assets/logo.jpg">
          </q-avatar>
          The Crazy Avocado Club
        </q-toolbar-title>
         <q-item v-if="connected" >
            <q-item-section side>
              <q-avatar color="green" size="28px">
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label style="color: black; font-family: 'Lucida Console';
                  font-weight: bold">{{account}}</q-item-label>
            </q-item-section>
          </q-item>
         <q-item v-else >
            <q-item-section side>
              <q-avatar color="red" size="28px">
              </q-avatar>
            </q-item-section>
            <q-item-section>
              <q-item-label style="color: black; font-family: 'Lucida Console';
                  font-weight: bold">You are not connected. Please connect your metamask wallet</q-item-label>
            </q-item-section>
          </q-item>
        <div class="row">
              <q-btn flat target="_blank" href="https://twitter.com/TCAC_Official" class="q-pa-lg" size="xl" color="black" icon="fab fa-twitter" />
              <q-btn flat target="_blank" href="https://discord.gg/vXw9u2XwQ6" class="q-pa-lg" size="xl" color="black" icon="fab fa-discord" />
            </div>
      </q-toolbar>

      <nav class="navbar">
        <div class="container">
          <ul>
            <q-btn size="20px" color="yellow-11" class="text-black" to="/">BACK HOME</q-btn>
          </ul>

        </div>
      </nav>  
    </q-header>

    <div>
      <p v-if="connected">You do not own any avocados yet. You can mint one when mint date begins on 26th Feb!</p>
      <p class="p2">If your avocados don't show up connect to Metamask and refresh the page</p>
    </div>
  </q-page>
</template>

<script>
import { ethers } from "ethers";
import abi from '../assets/abi.json'
import { parseBytes32String } from '@ethersproject/strings';
var contract

export default {
  data() {
    return {
      contractAddress: '0x861E99329cd05Dcff865141D8947b88d8271e909',
      connected: false,
      account: '',
    }
  },
  methods: {
    async doWeb3Shit() {
      if(window.ethereum){
         window.ethereum.request({method: 'eth_requestAccounts'})
         .then(result => {
           this.account = result[0]
           this.connected = true
         })
       } else {
         alert('Please connect your Metamask wallet')
         return
       }
      let provider = new ethers.providers.Web3Provider(window.ethereum);
      let signer = provider.getSigner();
      contract = new ethers.Contract(this.contractAddress, abi, signer);
    }
  },
  mounted() {
    window.addEventListener("DOMContentLoaded", function(event) {
      ethereum.on("chainChanged", () => window.location.reload());

        ethereum.on("accountsChanged", (accounts) => {
            if (accounts.length > 0) {
                console.log(`Using account ${accounts[0]}`);
            } else {
                console.error("0 accounts.");
            }
        });
    })
    this.doWeb3Shit()
  }
}
</script>

<style scoped>
 .q-page{
  background-color: rgb(173, 238, 69);
  /* background-color: rgb(208, 255, 133); */
  background-size: cover;

} 
nav {
  position: sticky;
  top: 0;
  background-color: black;
}
nav .container {
  width: 100%;
  max-width: 1000px;
  margin: 0 auto;
  text-align: center;
  padding: 5px;
}
nav .container ul {
  list-style: none;
  font-size: 24px;
  
}
nav .container ul li{
  display: inline-block;
  
}
nav .container ul li p{
  font-family: "Lucida Console";
  font-weight: bold;
  display: inline-block;
  padding: 10px 20px;
  color: #fffdf0;
  text-decoration: none;
}
p{
  font-family: "Lucida Console";
  font-weight: bold;
  color: black;
  text-align: center;
  text-decoration: none;
  font-size: 32px;
}
.p2{
  font-family: "Lucida Console";
  font-weight: bold;
  color: black;
  text-decoration: none;
  text-align: center;
  font-size: 22px;
}
.q-btn{
  font-family: "Lucida Console";
  font-weight: 500;
  color: #fffdf0;
  text-decoration: none;
}
nav .container ul li.active p{
  color: #FFFFA7;
  text-decoration-line: underline !important;
  text-decoration-thickness: 10px;
  transition: 0.3 ease text-decoration;

}
</style>