<template>
  <v-card >
      <v-tabs
        v-model="tabs"
        centered
        id='tabNavMenu'
      >
        <v-tab>          
            <v-icon color="var(--primary)"> fa fa-cart-shopping</v-icon>
            <v-spacer></v-spacer>
            Carrinho
        </v-tab>
        <v-tab>
            <v-icon color="var(--primary)"> fa fa-tags</v-icon>            
            <v-spacer></v-spacer>
            Descontos
        </v-tab>
        <v-tab>
            <v-icon color="var(--primary)"> fa fa-sack-dollar</v-icon>
            <v-spacer></v-spacer>
            Pagamentos
        </v-tab>
      </v-tabs>
        <v-divider></v-divider>
      <v-tabs-items v-model="tabs" >
      <v-tab-item>
        <ItemCard />
      </v-tab-item>
      <v-tab-item>
        <CupomDescontoCard />
      </v-tab-item>
      <v-tab-item>
        <PagamentoCard />
      </v-tab-item>
    </v-tabs-items>
  </v-card>
</template>

<script>
  import ItemCard from './ItemsCard.vue'
  import CupomDescontoCard from './CupomDescontoCard.vue'
  import PagamentoCard from './PagamentoCard.vue'
  export default {
    name:'TabCaixaCard',
    computed:{
        qtdItens(){
        return this.$store.state.caixa.qtdItens
      },
    },
    data () {
      return {
        tabs: null,       
      }
    },
    components:{
        ItemCard,
        CupomDescontoCard,
        PagamentoCard,
    }
  }
</script>
<style>
#tabNavMenu{
  border-radius: 3px;
  max-height: 15%;
}


</style>