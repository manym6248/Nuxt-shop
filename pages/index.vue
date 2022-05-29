<template>
  <div>
    <div class="slider1">
      <v-carousel height="100%" hide-delimiters>
        <v-carousel-item v-for="(item, i) in carousel" :key="i">
          <v-sheet :color="item.color" height="100%">
            <v-container class="container">
              <v-row
                class="
                  rowcarousel
                  fill-height
                  my-0
                  mx-lg-10 mx-xl-10 mx-md-10 mx-sm-10 mx-0
                "
                align="center"
                justify="center"
              >
                <v-col cols="12" xl="7" lg="7" md="7" sm="7">
                  <h1 class="carousel-titel mb-10">{{ item.title }}</h1>
                  <p class="carousel-text text-justify">
                    {{ item.text }}
                  </p>
                  <v-row justify="end" class="ma-0">
                    <v-btn
                      elevation="3"
                      class="carousel-btn mt-10 ml-5 primary rounded-xl"
                      x-large
                      >بریم برای خرید</v-btn
                    >
                  </v-row>
                </v-col>
                <v-col
                  lg="5"
                  xl="5"
                  md="5"
                  sm="5"
                  v-if="!$vuetify.breakpoint.xs"
                >
                  <img class="carousel-img" :src="item.src" />
                </v-col>
              </v-row>
            </v-container>
          </v-sheet>
        </v-carousel-item>
      </v-carousel>
    </div>
    <v-container>
      <article class="mt-10">
        <div class="text1">
          <h2 class="mb-3">ارائه محصولات با کیفیت و با دوام</h2>
          <p>
            در فروشگاه کیف و کفش ما دست تان باز بوده و می توانید هر مدلی که
            خواستید را پیدا کنید
          </p>
          <productssliders></productssliders>
        </div>
      </article>
    </v-container>
    <article>
      <v-parallax dark :src="src" height="300">
        <v-row>
          <v-col cols="6" class="pa-0">
        <div class="bigcard2">
             
                <v-container>
                  <v-row align="center" justify="center">
                    <p class="pa-10 pb-0 mt-0">
                      در ایام تابستون دوست دارید کیف و کفشی مناسب با همین فصل را
                      خریداری کنید. فروشگاه ما، با مدل ها و طرح های متنوع خود،
                      شما را در خرید یاری خواهد کرد و بهترینِ آن چرا که
                      میخواستید تقدیم حضورتان می کند.
                    </p>
                    <v-btn color="primary" class="rounded-xl mt-0"
                      >بریم برای خرید</v-btn
                    >
                  </v-row>
                </v-container>
             
            </div>
          </v-col>
          <v-col cols="6" class="pa-0">
            <div class="bigcard2">
             
                <v-container>
                  <v-row align="center" justify="center">
                    <p class="pa-10 pb-0 mt-0">
                      در ایام تابستون دوست دارید کیف و کفشی مناسب با همین فصل را
                      خریداری کنید. فروشگاه ما، با مدل ها و طرح های متنوع خود،
                      شما را در خرید یاری خواهد کرد و بهترینِ آن چرا که
                      میخواستید تقدیم حضورتان می کند.
                    </p>
                    <v-btn color="primary" class="rounded-xl mt-0"
                      >بریم برای خرید</v-btn
                    >
                  </v-row>
                </v-container>
             
            </div>
          </v-col>
        </v-row>
      </v-parallax>
    </article>

    <v-container>
      <article class="mt-10">
        <div class="text1">
          <h2 class="mb-3">ارائه محصولات با کیفیت و با دوام</h2>
          <p>
            در فروشگاه کیف و کفش ما دست تان باز بوده و می توانید هر مدلی که
            خواستید را پیدا کنید
          </p>
          <productssliders></productssliders>
        </div>
      </article>
    </v-container>
    <article>
      <v-parallax dark :src="src" height="300">
        <v-container class="container">
          <v-row
            class="
              rowcarousel
              fill-height
              my-0
              mx-lg-10 mx-xl-10 mx-md-10 mx-sm-10 mx-0
            "
            align="center"
            justify="center"
          >
            <v-col cols="12" xl="12" lg="12" md="12" sm="12">
              <h1 class="carousel-titel mb-10">با ما شیک و مدرن باشید</h1>
              <p class="carousel-text text-justify">
                بهترین ها را از ما بخواهید. عرضه کننده کیف و کفش هایی اصل در
                فروشگاه مغان شوز. به ده نفر اولی که برای خرید کیف و کفش های فلان
                به فروشگاه ما مراجعه میکنن، پنچاه درصد تخفیف داده خواهد شد.
                بشتابید و تا فرصت به اتمام نرسیده از این تخفیف استثنایی استفاده
                کنید.
              </p>
              <v-row
                justify="end"
                class="ma-0"
                v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs"
              >
                <v-btn
                  elevation="3"
                  class="carousel-btn mt-10 ml-5 primary rounded-xl"
                  x-large
                  >بریم برای خرید</v-btn
                >
              </v-row>
            </v-col>
          </v-row>
        </v-container>
      </v-parallax>
    </article>
  </div>
</template>

<script>
import Productssliders from "~/components/Productssliders.vue";

export default {
  components: { Productssliders },

  name: "IndexPage",
  data() {
    return {
      flickityOptions: {
        initialIndex: 4,
        prevNextButtons: false,
        pageDots: false,
        wrapAround: true,

        autoPlay: 3500,
        // any options from Flickity can be used
      },
      src: require("../assets/png/paralax/6.webp"),
      src1: require("../assets/png/2.png"),
      src2: require("../assets/png/3.png"),

      carousel: [
        {
          color: "indigo",
          text: "بهترین ها را از ما بخواهید. عرضه کننده کیف و کفش هایی اصل در فروشگاه مغان شوز. به ده نفر اولی که برای خرید کیف و کفش های فلان به فروشگاه ما مراجعه میکنن، پنچاه درصد تخفیف داده خواهد شد. بشتابید و تا فرصت به اتمام نرسیده از این تخفیف استثنایی استفاده کنید.",
          title: "ارائه محصولات با کیفیت و با دوام",
          src: require("../assets/png/1.png"),
        },
        {
          color: "warning",
          text: "در ایام زمستان دوست دارید کیف و کفشی مناسب با همین فصل را خریداری کنید. فروشگاه ما، با مدل ها و طرح های متنوع خود، شما را در خرید یاری خواهد کرد و بهترینِ آن چرا که میخواستید تقدیم حضورتان می کند.",
          title: "با ما شیک و مدرن باشید",
          src: require("../assets/png/2.png"),
        },
        {
          color: "red lighten-1",
          text: "در ایام تابستون دوست دارید کیف و کفشی مناسب با همین فصل را خریداری کنید. فروشگاه ما، با مدل ها و طرح های متنوع خود، شما را در خرید یاری خواهد کرد و بهترینِ آن چرا که میخواستید تقدیم حضورتان می کند.",
          title: "مد از پا شروع میشه",
          src: require("../assets/png/3.png"),
        },
      ],
    };
  },
};
</script>
<style lang="scss" >
.text1 {
  h2,
  p {
    text-align: center;
  }
}


.bigcard2 {
  .container {
    height: 100%;
    .row {
      height: 100%;
      p {
        color: beige;
        text-align: center;
        
      }
    }
  }
  height: 400px;
  width: 100%;

}

.slider1 {
  * {
    color: white;
  }
  height: 100vh;
  width: 100%;
  background-color: red;
  .container {
    height: 100%;
  }
  .rowcarousel {
    width: 100%;
  }
  .carousel-titel {
    text-shadow: 0px 1px 4px;
    animation: move 1.3s ease-in-out forwards;
    opacity: 0;
  }
  .carousel-text {
    animation: move2 1s ease-in-out forwards;
    opacity: 0;
  }
  .carousel-img {
    animation: move3 1.5s ease-in-out forwards;
    opacity: 0;
  }
  .carousel-btn {
    animation: move2 1s ease-in-out forwards;
    opacity: 0;
  }
}

@keyframes move {
  from {
    transform: translateX(200px);
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}
@keyframes move2 {
  from {
    transform: translateY(200px);
  }
  to {
    transform: translateY(0px);
    opacity: 1;
  }
}
@keyframes move3 {
  from {
    transform: translateX(-200px);
  }
  to {
    transform: translateX(0px);
    opacity: 1;
  }
}
</style>
