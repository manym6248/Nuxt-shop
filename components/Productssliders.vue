<template>
  <div class="text2">
    <v-row ma-0 class="sliderrowCards">
      <Flickity class="box" :options="flickityOptions">
        <v-col
          class="py-0 carousel-cell"
          cols="6"
          sm="6"
          md="3"
          lg="3"
          xl="3"
          v-for="item in 10"
          :key="item"
        >
          <v-card class="mt-5 boxCard" width="100%" height="350" elevation="2">
            <v-img :src="src" contain aspect-ratio="1.7" height="70%"> </v-img>

            <v-card-title class="titleCard pb-0 mb-n2"
              >Cafe Badilico</v-card-title
            >
            <v-card-text class="btnCard">
              <div class="text-subtitle-1">ریال 3000,000</div>
              <v-spacer></v-spacer>
              <v-tooltip bottom>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    large
                    icon
                    color="primary"
                    v-bind="attrs"
                    v-on="on"
                    class="pt-0"
                  >
                    <v-icon>mdi-cart-outline </v-icon>
                  </v-btn>
                </template>
                <span>افزودن به سبد خرید</span>
              </v-tooltip>
              <v-tooltip bottom>
                <template v-slot:activator="{ on, attrs }">
                  <v-btn
                    large
                    icon
                    color="primary"
                    v-bind="attrs"
                    v-on="on"
                    class="pt-0"
                  >
                    <v-icon>mdi-heart </v-icon>
                  </v-btn>
                </template>
                <span> افزودن به علاقه مندی ها </span>
              </v-tooltip>
            </v-card-text>
          </v-card>
        </v-col>
      </Flickity>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      flickityOptions: {
        initialIndex: 4,
        prevNextButtons: true,
        pageDots: false,
        wrapAround: true,
        groupCells: 2,
        //autoPlay: 7000,
        // any options from Flickity can be used
      },
      src: require("../assets/png/1.png"),
    };
  },
  watch: {},
};
</script>

<style lang="scss" scoped >
.flickity-button {

  background: transparent;
  &:hover{

    background-color: $color-primary3 ;
    .flickity-button-icon {
  fill: $color-primary3;
}
  }
    .flickity-button-icon {
  fill: $color-primary3;
}
}

.sliderrowCards {
 
  height: 100%;
  .carousel-cell {
    height: 100%;
  }
}
.text2 {
  height: 400px;
  .box {
    width: 100%;
    height: 100%;
    .carousel-cell {
      width: 100%;
    }

    .boxCard {
      &:hover {
        box-shadow: 0px 0px 7px $color-primary !important;
      }

      .titleCard {
        color: lighten($color: $color-primary, $amount: 5);
      }
      .btnCard {
        display: flex;
        flex-direction: row;
        align-items: center;
      }
      .text-subtitle-1 {
        color: lighten($color: $color-primary, $amount: 10);
      }
    }
  }
}
</style>