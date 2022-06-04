<template>
  <div class="footerdiv ma-0">
    <v-row justify="center" class="footerrow ma-0">
      <v-col cols="3" v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs" >
        <h3>خدمات مشتریان</h3>
        <ul class="items">
          <li class="item"><nuxt-link to="/">تماس با ما</nuxt-link></li>
          <li class="item"><nuxt-link to="/">استرداد کالا</nuxt-link></li>
          <li class="item"><nuxt-link to="/">نقشه سایت</nuxt-link></li>
          <li class="item"><nuxt-link to="/"> تولید کنندگان </nuxt-link></li>
        </ul>
      </v-col>
      <v-col cols="3" v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs">
        <h3>حساب کاربری من</h3>
        <ul class="items">
          <li class="item"><nuxt-link to="/">حساب کاربری من</nuxt-link></li>
          <li class="item"><nuxt-link to="/"> تاریخچه سفارش ها</nuxt-link></li>
          <li class="item"><nuxt-link to="/">لیست دلخواه</nuxt-link></li>
          <li class="item"><nuxt-link to="/">کالاهای ویژه</nuxt-link></li>
        </ul>
      </v-col>
      <v-col cols="3" v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs">
        <h3>تماس با ما</h3>
        <ul class="items">
          <li class="item"><nuxt-link to="/">درباره ما</nuxt-link></li>
          <li class="item"><nuxt-link to="/">حفظ حریم شخصی</nuxt-link></li>
          <li class="item"><nuxt-link to="/">شرایط و قوانین</nuxt-link></li>
          <li class="item"><nuxt-link to="/">ثبت شکایت</nuxt-link></li>
          <li class="item"><nuxt-link to="/">نحوه سفارش</nuxt-link></li>
          <li class="item"><nuxt-link to="/">روند بازگشت کالا</nuxt-link></li>
        </ul>
      </v-col>
      <v-col cols="12" lg="3" xl="3" md="3" >
        <h3  v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs">خبرنامه</h3>

        <div class="list" v-if="$vuetify.breakpoint.sm || $vuetify.breakpoint.xs">
             <v-list  class="mt-5 rounded-xl">
      <v-list-group
     
        v-for="(item, i) in array"
        :key="i"
        no-action
      >
        <template v-slot:activator>
          <v-list-item-content>
            <v-list-item-title v-text="item.title"></v-list-item-title>
          </v-list-item-content>
        </template>

        <v-list-item
          v-for="(child, i) in item.items"
          :key="i"
        >
          <v-list-item-content>
            <v-list-item-title v-text="child.title"></v-list-item-title>
          </v-list-item-content>
        </v-list-item>
      </v-list-group>
    </v-list>
        </div>
        <ul class="items pl-0">
          <li class="item">
            <nuxt-link to="/">در خبر نامه سایت عضو شوید.</nuxt-link>
          </li>
          <div class="search-box2 mt-3">
            <input class="input" type="text" placeholder="ایمیلتو بزن" />
            <v-btn color="primary"  class="rounded-xl">
              <v-icon>mdi-send-circle</v-icon>
            </v-btn>
          </div>
          <v-row class="ma-0 mt-3" justify="center">
            <v-btn icon><v-icon>mdi-instagram</v-icon></v-btn>
            <v-btn icon><v-icon>mdi-linkedin</v-icon></v-btn>
            <v-btn icon><v-icon>mdi-twitter</v-icon></v-btn>
          </v-row>
        </ul>
      </v-col>
    </v-row>
    <v-container v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs">
      <h2 class="mt-5" >
        فروشگاه اینترنتی مغان شوز بررسی , مقایسه , خرید آنلاین
      </h2>
      <p class="mt-3 mb-15">
        مغان شوز بزرگترین فروشگاه اینترنتی با عنایت پروردگار و حمایت شما مشتریان
        گرامی , فعالیت خود با محصولات متنوع و و مد روز یک خرید لذت بخش بدون صرف
        وقت و هزینه برای خارج شدن از منزل را برای هم وطنان عزیز فراهم کرده است.
        اصول اولیه مغان شوز ارسال سریع کالا , ضمانت بهترین قیمت و تضمین اصل بودن
        کالا می باشد و با رعایت این سه اصل تلاش کرده ایم محصولات متنوع و کاربردی
        بیشتری متناسب با نیاز مشتریان خود با برند های معتبر ایرانی و خارجی را به
        حوزه فعالیت خود اضافه نمائیم و به صورت فعال و پویا با انگیزه ای مضاعف
        آماده خدمت رسانی به هم وطنان عزیز در سراسر ایران باشیم.
      </p>
    </v-container>
    <div class="end pt-xl-3 pt-lg-3 pt-md-3">
      <v-row justify="center"  class="ma-0">
        <v-col cols="12" lg="5" md="6" xl="5" class="pa-0 pt-2 pr-xl-16 pr-lg-16 pr-md-5 pr-4 ">
          <span
            >کلیه حقوق این سایت متعلق به فروشگاه مغان شوز می باشد
          </span>
        </v-col  >
        <v-col class="pa-0 pt-2 pr-16" lg="4" md="6" xl="4"  v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs"  >
          <span icon >2239-2022 © copyright </span>
        </v-col  >
        <v-col class="pa-0 pt-2 pr-16" lg="2"  xl="2"  v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs && !$vuetify.breakpoint.md" >
          <span  >مغان شوز</span>
        </v-col>
      </v-row>
    </div>
  </div>
</template>

<script>
export default {

    data(){
        return{
            array:[
               {title:"خدمات مشتریان",
               items:[
                   {title:"تماس با ما"},
                   {title:"استرداد کالا"},
                   {title:"نقشه سایت"},
                   {title:"تولید کنندگان "},
               ]
               },
               {title:"حساب کاربری من",
               items:[
                   {title:"حساب کاربری من"},
                   {title:"تاریخچه سفارش ها"},
                   {title:"لیست دلخواه"},
                   {title:"کالاهای ویژه"},
               ]
               },
               {title:"تماس با ما",
               items:[
                   {title:"درباره ما"},
                   {title:"حفظ حریم شخصی"},
                   {title:"شرایط و قوانین"},
                   {title:"ثبت شکایت"},
                   {title:"نحوه سفارش"},
                   {title:"روند بازگشت کالا"},
               ]
               },

            ]
        }
    }
};
</script>

<style lang="scss" scoped>
.footerdiv {
  width: 100%;
  .end {
    width: 100%;
    height: 65px;
    background-color: $color-primary2;
    span{
        color:beige;
    }
  }
}
h3,
h2,
p {
  text-align: center;
  margin-top: 20px;
  color: white;
}
.footerrow {
  width: 100%;
  .items {
    display: flex;
    flex-direction: column;
    margin-top: 20px;
    color: aliceblue;

    .item {
        text-align: center;
      margin: 6px;
      a {
          color: aliceblue;
        padding: 12px;
      }
    }
  }
  .search-box2 {
    background-color: azure;
    margin-left: 12px;
    width: 100%;
    height: 45px;
    display: flex;
    flex-direction: row;
    border-radius: 50px;
    position: relative;

    .v-btn {
      position: absolute;
      left: 3px;
      bottom: 5px;
    }
    .input {
      color: #000;
      position: absolute;
      display: none;
      height: 100%;
      border: none;
      width: 80%;
      padding: 10px;
      display: block;
      outline: none;
    }
  }
}
</style>