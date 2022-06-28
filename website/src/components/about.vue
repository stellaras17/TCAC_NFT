<template>
  <div style="width: 100%, ">
      <h3 class="flex flex-center"> ABOUT </h3>
      <div class=" flex flex-center row center-div" style="margin:0 auto;width: 80%; align-items: center;">
        <q-img
          class="q-mr-xs image-style"
          src="../assets/preview.gif"
          :ratio="1"
          style="min-width:170px; min-height:170px"
          width="35%"
          height="35%"
        />
        <div class="div-p" style="width:35%; margin-top:0 !important" >
          <p style="text-align: right">
            Our club is a collection of 10000 unique avocados on the Ethereum blockchain. 
            The project was built with the sole purpose of helping the environment. 
            For each NFT mint the team will plant trees and donate money for animal rescuing!
          </p>
        </div>
      </div>
      
      <div class="q-mt-xl flex flex-center row center-div column" style="margin:0 auto;width: 80%; align-items: center;">
          <h4>The GEM pit</h4>
          <div class=" q-pa-sm collumn flex flex-center" style="background-color: #ebff7b; border-radius: 25px;">
            <q-img src="../assets/gem.png" width="30%" height="30%"/>

            <p class="gem-p" style="text-align: center; width: 60%">
              Rare avocados who have the GEM pit will get their owners awarded with 0.5 ETH after the free mint.
            </p>
          </div>

      </div>

  </div>
</template>

<script>
export default {

}
</script>

<style lang="scss" scoped>
@media screen and (max-width: 768px){
  .image-style{
    display: none;
  }
  .div-p{
    width: 100% !important;
  }
  .center-div{
      display: flex;
      justify-content: center;
     
  }
  .center-div p{
      text-align: center !important;
  }

  .gem-p {
    font-size: 16px;
  }
}
  
  p{
  color: black;
  font-weight: 800;
  font-family: "Lucida Console";
  font-size: 24px;
  }
  h4{
  color: black;
  font-weight: 800;
  font-family: "Lucida Console";
  }
  h3{
  color: black;
  font-family: "Lucida Console";
  font-weight: 900;
  text-decoration-line: underline;
  text-decoration-thickness: 10px;
  transition: 0.3 ease text-decoration;
}
</style>