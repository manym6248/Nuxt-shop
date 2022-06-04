<template>
  <div>
    <v-container class="mt-16 mb-3">
      <v-row class="ma-3" justify="center">
        <v-col cols="12" xl="4" lg="4" md="4" sm="6">
          <v-card>
            <InnerImageZoom
             
              :src="product.image"
              :zoomSrc="product.image"
              class="imgzoom"
            />
          </v-card>
        </v-col>
        <v-col cols="12" lg="8" xl="8" md="8" sm="6">
          <v-card height="100%" color="pa-4">
            <h1 class="mb-5 mr-4">
              {{ product.name }}
            </h1>
            <v-row class="ma-0 mb-5 align-center">
              <h3 class="mr-4">تومان {{ product.price }}</h3>
              <span class="mr-4 discount">
                {{ product.discount }}% تخفیف ویژه
              </span>
            </v-row>
            <v-card-text>{{ product.description }}</v-card-text>
            <v-row class="ma-0"> </v-row>
            <v-row class="ma-0 align-center">
              <p class="mt-4 pt-2 ml-3 ma-0 pa-0">اندازه ها:</p>
              <v-radio-group
                v-model="direction"
                v-for="(item2, i) in product.Sizes"
                :key="i"
              >
                <v-radio
                  class="mt-1 ml-10 input1"
                  value="top"
               
                ></v-radio>
              </v-radio-group>
            </v-row>
            <v-row class="ma-0 align-center">
              <p class="mt-4 pt-2 ml-3 ma-0 pa-0">رنگ ها:</p>
              <v-radio-group
                v-model="direction"
                v-for="(item3, i) in product.colors"
                :key="i"
              >
                <v-radio
                  class="mt-1 mb-10 ml-10 input1"
                  value="top"
                 
                ></v-radio>
              </v-radio-group>
            </v-row>

            <v-tooltip bottom>
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                  color="primary"
                  v-bind="attrs"
                  v-on="on"
                  class="mt-10 mb-5 mr-3"
                >
                  <v-icon>mdi-cart-outline </v-icon>
                  خرید
                </v-btn>
              </template>
              <span>افزودن به سبد خرید</span>
            </v-tooltip>
            <v-tooltip bottom>
              <template v-slot:activator="{ on, attrs }">
                <v-btn
                  color="primary"
                  v-bind="attrs"
                  v-on="on"
                  class="mt-10 mb-5 ml-3"
                >
                  <v-icon>mdi-heart </v-icon>
                  علاقمندی
                </v-btn>
              </template>
              <span> افزودن به علاقه مندی ها </span>
            </v-tooltip>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
    <v-container class="px-6">
     
        <v-tabs v-model="tabs"  color="deep-purple accent-4">
          <v-tabs-slider></v-tabs-slider>
          <v-tab  class="primary--text">
            توضیحات
          </v-tab>

          <v-tab  class="primary--text">
         اطلاعات بیشتر
          </v-tab>

          <v-tab   class="primary--text">
            نظرات
          </v-tab>
        </v-tabs>

        <v-tabs-items v-model="tabs" class="mt-3">
         
          <v-tab-item   >
            <v-card flat class="tab-sheet">
              <v-card-title>پارگراف</v-card-title>
              <v-card-text >
                  لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با
                استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله
                در ستون و سطرآنچنان که لازم است ولورم ایپسوم متن ساختگی با تولید
                سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
                  لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با
                استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله
                در ستون و سطرآنچنان که لازم است ولورم ایپسوم متن ساختگی با تولید
                سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
                  لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با
                استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله
                در ستون و سطرآنچنان که لازم است ولورم ایپسوم متن ساختگی با تولید
                سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
              </v-card-text>
            </v-card>
          </v-tab-item>
          <v-tab-item   >
            <v-card flat class="tab-sheet">
              <v-card-title>پارگراف</v-card-title>
              <v-card-text >
                  لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با
                استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله
                در ستون و سطرآنچنان که لازم است ولورم ایپسوم متن ساختگی با تولید
                سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
                  لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با
                استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله
                در ستون و سطرآنچنان که لازم است ولورم ایپسوم متن ساختگی با تولید
                سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
                  لورم ایپسوم متن ساختگی با تولید سادگی نامفهوم از صنعت چاپ و با
                استفاده از طراحان گرافیک است. چاپگرها و متون بلکه روزنامه و مجله
                در ستون و سطرآنچنان که لازم است ولورم ایپسوم متن ساختگی با تولید
                سادگی نامفهوم از صنعت چاپ و با استفاده از طراحان گرافیک است.
              </v-card-text>
            </v-card>
          </v-tab-item>
         
          <v-tab-item   >
            <v-card flat class="tab-sheet">
              <v-card-text  v-text="text"></v-card-text>
            </v-card>
          </v-tab-item>
        </v-tabs-items>
     
    </v-container>
      <v-container>
      <article class="mt-10">
        <div class="text1">
          <h2 class="mb-3">محصولات  مرتبت</h2>
          <p>
            در فروشگاه کیف و کفش ما دست تان باز بوده و می توانید هر مدلی که
            خواستید را پیدا کنید
          </p>
          <productssliders></productssliders>
        </div>
      </article>
    </v-container>
  </div>
</template>

<script>
import InnerImageZoom from "vue-inner-image-zoom";
import Productssliders from "~/components/Productssliders.vue";
import { mapGetters } from 'vuex'
export default {
  components: {
    InnerImageZoom,
    Productssliders
  },
  data() {
    return {
      direction:false,
      tabs: null,
      text: "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
       page:null
    };
  },
  asyncData({isDev, route, store, env, params, query, req, res, redirect, error}) {
    c
  },
  computed:{
   
  product:{
      get () {
          
        return this.$store.getters['product/findproduct'](this.page)
        },
  },
  },
  created() {
    this.page =this.$route.params.id
  },
  
};
</script>

<style lang="scss" scoped>
.imgzoom {
  height: 100%;
  width: 100%;
}
.discount {
  width: 130px;
  height: 31px;
  color: #9b27b0;
  background-color: thistle;
  padding: 4px;
  border-radius: 50px;
}
.v-input {
  height: 30px;
}

///tab
.v-tab{
  letter-spacing: 0;

}
.tab-sheet{
  background-color:thistle;
  height: 350px;
  padding: 20px;

  
}
.v-card__text{
  text-align:justify ;

}

</style>