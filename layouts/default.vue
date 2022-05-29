<template>
  <v-app dark>
    <v-navigation-drawer
      v-model="rightDrawer"
      :right="right"
      temporary
      fixed
      app
    >
      <v-list-item>
        <v-list-item-content>
          <v-list-item-title class="text-h6"> Application </v-list-item-title>
          <v-list-item-subtitle> subtext </v-list-item-subtitle>
        </v-list-item-content>
        <v-btn icon @click.stop="rightDrawer = !rightDrawer">
          <v-icon>mdi-menu</v-icon>
        </v-btn>
      </v-list-item>

      <v-divider></v-divider>

      <v-list>
        <v-list-item
          @click.native="right = !right"
          v-for="(item, i) in items"
          :key="i"
          :to="item.to"
          router
          exact
        >
          <v-list-item-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-item-action>
          <v-list-item-content>
            <v-list-item-title v-text="item.title" />
          </v-list-item-content>
        </v-list-item>
      </v-list>
    </v-navigation-drawer>
    <v-app-bar class="px-3 py-0"  fixed elevation="0" :class = " headerbar ? 'color' : 'transparent' ">
      <v-toolbar-title  v-text="title" />
      <ul
        v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs"
        class="items mr-3"
      >
        <li class="item">
          <nuxt-link to="/">صحفه اصلی</nuxt-link>
        </li>
        <li class="item">
          <nuxt-link to="/">فروشگاه</nuxt-link>
        </li>
        <li class="item">
          <nuxt-link to="/">درباره ما</nuxt-link>
        </li>
      </ul>
      <v-spacer />
      <div class="search-box" v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs">
          <input class="input" type="text" placeholder="search">
        <v-btn icon color="primary" small>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>
      </div>
       <v-btn color="white" icon>
        <v-icon>mdi-cart-outline</v-icon>
      </v-btn>
      <v-btn color="white" icon v-if="!$vuetify.breakpoint.sm && !$vuetify.breakpoint.xs">
        login
      </v-btn>

      <v-btn color="white" v-else icon @click.stop="rightDrawer = !rightDrawer">
        <v-icon>mdi-menu</v-icon>
      </v-btn>
     
    </v-app-bar>
    <v-main>
      <Nuxt />
    </v-main>

    <v-footer  class="px-0 pb-0">
      <footer-box></footer-box>
    </v-footer>
  </v-app>
</template>

<script>
import FooterBox from '~/components/FooterBox.vue';
export default {
  components: { FooterBox },
  name: "DefaultLayout",
  data() {
    return {
      drawer: false,
      headerbar:false,

      items: [
        {
          icon: "mdi-apps",
          title: "Welcome",
          to: "/",
        },
        {
          icon: "mdi-chart-bubble",
          title: "Inspire",
          to: "/inspire",
        },
      ],
      miniVariant: false,
      right: true,
      rightDrawer: false,
      title: "مغان شوز",
    };
  },
  mounted(){
  
    window.addEventListener('scroll' , ()=>{
      if(scrollY > 50){
       this.headerbar = true;
       
      }
      else{
         this.headerbar = false;
      }

    })
  }
};
</script>
<style lang="scss" scoped >

@import "../assets/variables.scss";

.v-footer{
  background-color: $color-primary3 !important;
}

.color{
  background-color: #9b27b0 !important;
}
.v-toolbar__title{
  font-weight: bold;
  color: white;
}
.items {
  display: flex;
  flex-direction: row;
  .item {
    a {
      color: white;
      padding: 12px;
    }
    &:hover {
      a {
        color: indigo accent-4 !important;
      }
    }
  }
}
.search-box {
  background-color: azure;
  margin-left: 12px;
  width: 35px;
  height: 35px;
  display: flex;
  flex-direction: row;
 
  border-radius: 50px;
  position: relative;
  &:hover {
    animation: move-box 1s ease-in-out forwards;
    .input {
      display: block;
    }
  }
  &:focus{
    width: 200px;
     .input {
      display: block;
    }
  }
    
  .v-btn {
    position: absolute;
    left: 3px;
    bottom: 3px;
  }
  .input {
    color: #000;
    position: absolute;
 
    display: none;
    height: 100%;
    border: none;
    width: 85%;
    padding: 10px;
    outline: none;
  }
}

@keyframes move-box {
  from {
    width: 35px;
  }
  to {
    width: 200px;
  }
}
</style>
