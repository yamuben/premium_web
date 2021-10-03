<template>
  <div class="container"  style="display:flex;">
    <div class="sidelayout">
      <h1 style="font-weight: bolder">
        <a-icon
          type="sliders"
          style="transform: rotate(90deg); color: #fe5e27"
        />
        Filtra Auto
      </h1>

<a-collapse v-model="activeKey" :expand-icon-position="expandIconPosition">
      <a-collapse-panel key="1" header="FACIO DI COSTO 100 KM" class="titlecollapse">
        <p style="font-size:12px">{{ text }}</p>
      </a-collapse-panel>
      <a-collapse-panel key="2" header="ALIMANTAZOINE" class="titlecollapse">
       

  <a-list  :data-source="data">
      <a-list-item slot="renderItem" slot-scope="item, index">

  <a-checkbox @change="onChange">
 
        {{ item.name }} (<span style="color:red">{{item.number}} </span>) 
  </a-checkbox>     
        </a-list-item>
    </a-list>


      </a-collapse-panel>

      <a-collapse-panel key="3" header="TIPO AUTO" class="titlecollapse">
       

  <a-card>
    <a-card-grid v-for="item in data" :key="item.message" style="width:50%; box-shadow:3px solid white;text-align:center">
      
  <a-checkbox @change="onChange">
 
        {{ item.name }} 
  </a-checkbox> 
    </a-card-grid>
  </a-card>

      </a-collapse-panel>
    </a-collapse>
   
    
    </div>
    <a-col class="bodylayout">

        <CarList/>
    </a-col>
  </div>
</template>

<script>
import data from "../assets/constants/listOfCheck.json";
import CarList from "./CarList.vue";
export default {
  name: "BodyLayout",
components:{
    CarList
},

  data() {
    return {
      text: `A dog is a type of domesticated animal.Known for its loyalty and faithfulness,it can be found as a welcome guest in many households across the world.`,
      activeKey: ['1'],
      expandIconPosition: 'right',
      title: "Premium Web",
      data
    };
  },
  watch: {
    activeKey(key) {
      console.log(">>>>",key);
    },
  },
  methods: {
    handleClick(event) {
      // If you don't want click extra trigger collapse, you can prevent this:
      event.stopPropagation();
    },
     onChange(e) {
      console.log(`checked = ${e.target.checked}`);
    },
  },
};
</script>

<style scoped>
.sidelayout {
  background: white;
  text-align: left;
  padding: 20px 0px 0px 50px;
  width: 35.6%;
  min-height: 100vh;
}
.titlecollapse{
    font-size: 20px;
    font-weight: bolder;
}
.bodylayout{
    width:64.4%;
    padding:0.6%;
    background:white;
}


@media only screen and (max-width: 768px) {
    .container{
        flex-wrap: wrap;
        background:white;
    }
    .sidelayout {
        width:90%;
        min-height:auto;
    }
    .titlecollapse{
        font-size: 15px;
    }
    .bodylayout{
        width: 100%;}
}
</style>