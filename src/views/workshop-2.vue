<template>
  <a-col :span="20">
    <h1 align="center">Workshop #1 - Calculate product price</h1>
    <a-row type="flex">
      <a-col :flex="1" justify="start">
        <a-row type="flex" :gutter="16">
          <a-col :span="7" v-for="item in products">
            <a-card hoverable style="width: auto">
              <template #cover>
                <img alt="example" :src="item.image" />
              </template>
              <a-card-meta :title="item.name">
                <template #description>
                    <h2>Price {{item.price}}</h2>
                </template>
              </a-card-meta>
              <div style="margin-top: 10px">
                <a-checkbox @change="selected(item)"></a-checkbox>
              </div>
            </a-card>
          </a-col>
        </a-row>
      </a-col>
        <a-col :flex="3"> 
            <h2>ยอดชำระเงิน : </h2>
        </a-col>
    </a-row>
  </a-col>
</template>
<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  methods:{
    selected:function(item){
        item.active = ! item.active
    },
    totel:function(){
      var sum =0;
      this.products.foreach(function(item)){
        if(item.active){
          sum+=item.price
        }
    }
    
  }
  },
  setup() {
    
    return {
      products: [
        {
          id: 1,
          name: "Product One",
          price: 150,
          image: "https://cdn-icons-png.flaticon.com/512/2674/2674505.png",
          active: false
        },
        {
          id: 2,
          name: "Product Two",
          price: 100,
          image: "https://cdn-icons-png.flaticon.com/512/2674/2674505.png",
          active: false
        },
        {
          id: 3,
          name: "Product Two",
          price: 95,
          image: "https://cdn-icons-png.flaticon.com/512/2674/2674505.png",
          active: false
        }
      ],
      sum;
    };
  },
  
});
</script>
