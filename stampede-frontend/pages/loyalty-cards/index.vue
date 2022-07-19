<template>

      <v-card class="card-container elevation-6">
        <v-card-title class="primary headline">
          <span class="text-leckerli">Customer Feedback Hero</span>
        </v-card-title>
        <v-card-subtitle class="primary">
          Answer 6 of our feedback polls and get a free IU hoody!
        </v-card-subtitle>
        <v-card-text class="pt-4">
          <div class="loyalty-card">
            <div class="loyalty-card--stamp-container text-leckerli">
              <div class="loyalty-card--stamp"><div><div class="stamp-bubble black--text success">1</div></div></div>
              <div class="loyalty-card--stamp"><div><div class="stamp-bubble black--text success">2</div></div></div>
              <div class="loyalty-card--stamp"><div><div class="stamp-bubble black--text success">3</div></div></div>
              <div class="loyalty-card--stamp"><div><div class="stamp-bubble black--text success">4</div></div></div>
              <div class="loyalty-card--stamp "><div><div class="stamp-bubble primary">5</div></div></div>
              <div class="loyalty-card--stamp "><div><div class="stamp-bubble primary">6</div></div></div>
            </div>
            <div class="loyalty-card--bonus">
              <div class="loyalty-card--bonus--icon primary">
              <v-icon size="4rem">mdi-tshirt-crew-outline</v-icon>
              </div>
              <v-btn class="mt-2" color="primary" nuxt to="/loyalty-cards"> Claim Bonus</v-btn>
            </div>
          </div>
        </v-card-text>
      </v-card>
</template>

<script>
export default {
  name: 'IndexPage',
}
</script>

<style lang="scss">
.card-container{
  max-width: 36rem;
}
.loyalty-card {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr 2fr;
  grid-template-areas:
    "header header header header"
    "stamp-container stamp-container stamp-container bonus"
    "stamp-container stamp-container stamp-container bonus";

  @media only screen and (max-width: 600px) {
    grid-template-columns: 1fr 1fr 1fr;
    grid-template-areas:

    "header header header"
    "stamp-container stamp-container stamp-container"
    "stamp-container stamp-container stamp-container"
    "bonus bonus bonus";

  }

  .loyalty-card--header {
    grid-area: header;
  }
  .loyalty-card--stamp-container{
    grid-area: stamp-container;
    display: grid;
    grid-gap: 1rem;
    grid-template-columns: 1fr 1fr 1fr;

    .loyalty-card--stamp {
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;

      .stamp-bubble{
        border-radius: 50%;
        height:4rem;
        width: 4rem;
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
      }
    }
  }

  .loyalty-card--bonus {
    grid-area: bonus;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;

    @media only screen and (max-width: 600px) {
      padding-top: 1rem
    }

    .loyalty-card--bonus--icon{
      border-radius: 50%;
      height:5rem;
      width: 5rem;
      padding: .5rem;
    }
  }

}


</style>
