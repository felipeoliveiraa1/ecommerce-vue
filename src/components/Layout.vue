<template>
  <v-app id="inspire">
    <v-app-bar
      :clipped-left="$vuetify.breakpoint.lgAndUp"
      color="white"
      app
    >
<!--      <v-app-bar-nav-icon @click.stop="drawer = !drawer" />-->

      <v-toolbar-title
        style="width: 350px"
      >
        <div class="font"><a href="/" class="black--text" style="text-decoration: none">Ateliê Rê Oliveira</a></div>
      </v-toolbar-title>
      <v-spacer />
      <v-btn icon color="black" href="/login">
        <v-icon>mdi-account-circle</v-icon>
      </v-btn>
      <v-btn v-on="on" color="black" href="/cart" icon>
        <v-badge
          content="2"
          value="2"
          color="grey"
          overlap
        >
          <v-icon>mdi-cart</v-icon>
        </v-badge>
      </v-btn>
    </v-app-bar>
    <v-content>
      <v-bottom-navigation
        :value="activeBtn"
        color="primary"
        horizontal
      >
        <a href="/" class="v-btn" >
          <span style="font-size: 1.1rem;">Início</span>
        </a>
        <v-menu open-on-hover offset-y>
          <template v-slot:activator="{ on }">
            <v-btn v-on="on">
              <span style="font-size: 1.1rem;">Produtos</span>
            </v-btn>
          </template>
          <v-card
            class="mx-auto"
            max-width="344"
            outlined
          >

            <v-list-item
              v-for="(item, index) in items"
              :key="index"
              @click="item"
              href="/shop"
            >
              <v-list-item-title>{{ item.title }}</v-list-item-title>
            </v-list-item>

          </v-card>
        </v-menu>
        <v-btn href="/post">
          <span style="font-size: 1.1rem;">Sobre</span>
        </v-btn>
      </v-bottom-navigation>
    </v-content>
      <router-view/>
    <v-footer
      :padless="true"
    >
      <v-card
        flat
        tile
        width="100%"
        class="secondary white--text text-center"
      >
        <v-card-text>
          <v-btn
            class="mx-4 white--text"
            icon
          >
            <v-icon size="24px">mdi-email</v-icon>
          </v-btn>

        </v-card-text>

        <v-card-text class="white--text pt-0">
          Produtos personalizados de todos os tipos!

          São Paulo - SP / Since  2018
        </v-card-text>
        <v-divider></v-divider>
        <ScrollTopArrow></ScrollTopArrow>
        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Design By: Felipe Oliveira :)</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>
<script>
  import ScrollTopArrow from '@/components/ScrollTopArrow'
    export default {
        data () {
            return {
                items: [
                    { title: 'T-Shirts' },
                    { title: 'Jackets' },
                    { title: 'Shirts' },
                    { title: 'Jeans' },
                    { title: 'Shoes' },
                ],
                activeBtn: 1,
            }
        },
        components: {
          ScrollTopArrow
        }
    } 
</script>
<style scoped>
@font-face {
  font-family: "Hogarth";
  src: url("../assets/fonts/hogarth-script-ef.ttf")
}
  .font {

        font-family: "Hogarth";
        font-size: 50px;
        font-weight: 500;
        letter-spacing: 3px;
        
    }
    @media(max-width: 500px){
    .font{
        font-size: 30px;
        color: black;
    }
    
}
</style>
